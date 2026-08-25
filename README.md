# SafetyEye

**Turns any phone into an offline workplace-safety monitor — and warns people *before* they cross the line.**

Built for the **iQOO Hackathon 2026 · Bengaluru City Battle** · Open Innovation track
Team **Fight Club** — Surendra Avula, Manasa Reddy

---

## The problem

Small construction sites, factories and warehouses are the workplaces where people are
most likely to get hurt, and they have no continuous safety monitoring at all. Not
because nobody cares — because the only product on the market means IP cameras,
cabling, a DVR or edge server, an uplink and a per-camera subscription. Roughly
₹2,00,000 to start. A contractor running an eight-month site will never buy it.

Meanwhile every supervisor on every one of those sites is already carrying a device
with a good camera and a processor that runs neural networks.

## What it does

Prop the phone facing a hazard. Draw a **danger zone** and a **fire exit** on the live
camera with your finger. Set a safe headcount. Then it watches:

| Rule | Fires when |
|---|---|
| Danger zone entered | A person is inside the area you marked |
| Too many people | Headcount in frame exceeds your limit |
| Fire exit blocked | A non-person object obstructs the exit zone |

Every violation is logged with a timestamp and a still frame. At shift end, one tap
produces a compliance report that opens in Word / Office Kit.

## What makes it different

Every camera-based safety system on the market is **forensic** — it documents breaches
after they happen. The worker who crossed into the machine zone finds out they broke a
rule when a supervisor reads a report the next day.

SafetyEye tracks how each person is moving, projects their path, and **speaks a warning
before they cross**. It only records a breach when the warning failed. So the report
leads with a number no forensic system can produce:

> **13 warnings called out · 6 breaches · 54% prevented**

This is only possible because the device is physically present and has a speaker. A
camera wired to a server room cannot shout.

## Privacy is architectural, not a policy

The detection model runs **on the device**. There is no server on the other end, so the
claim that footage never leaves the phone is a property of the architecture rather than
a promise. Turn the network off and it behaves identically.

The live view and the on-device log show people clearly — a supervisor cannot intervene
if they cannot tell who to call out to. The **exported report is blurred**, because the
client, auditor or insurer needs to know *that* a zone was breached, not *who* breached
it.

> The supervisor sees everything. The paperwork sees nobody.

## Running it

No build step, no dependencies to install.

```bash
git clone https://github.com/manasareddycherukupalli-cyber/safety-eye-.git
cd safety-eye-
python -m http.server 8000
```

Then open <http://localhost:8000>.

The camera needs a secure context, so use `localhost` or HTTPS — opening the file
directly over `file://` will have the camera blocked. On a phone, serve it over HTTPS
(GitHub Pages, or a tunnel).

If the camera is unavailable, the app falls back to a **simulated site** that runs the
same rules engine against synthetic detections.

## How it works

- **Detector** — [COCO-SSD](https://github.com/tensorflow/tfjs-models/tree/master/coco-ssd)
  (MobileNet backbone) via TensorFlow.js, executed entirely in the device runtime.
  No inference server, no API key.
- **Rules layer** — the model finds people and objects; the safety logic (zone
  geometry, occupancy, obstruction) is ours. This is how you ship without a labelled
  dataset.
- **Tracker** — detections are matched frame to frame by IoU and eased toward their
  measurements, giving each person a smoothed trajectory and surviving the dropped
  frames a detector produces constantly.
- **Prediction** — that trajectory is projected forward ~0.75s. If someone outside the
  zone is closing on it fast, the warning fires.
- **Decoupled loops** — inference runs to a target rate while the overlay draws at
  60fps against interpolated boxes. Throttled deliberately: a monitor has to last a
  whole shift, so pinning the processor would flatten the battery first.
- **Persistence** — zones, settings and the day's alerts with photographs survive a
  reload or the phone locking. A record that evaporates is not a record.
- **Built for the deployment** — screen wake lock so a propped phone doesn't sleep,
  haptics, spoken alerts, and correct behaviour when the network drops.

## Honest scope

The detector recognises **people and generic objects, not hard hats.** Today the app
enforces zone intrusion, occupancy and blocked egress. PPE detection is the same
pipeline with a fine-tuned model swapped in — the architecture is deliberately
model-agnostic.

Anonymisation blurs the **whole frame**, not detected faces. Masking only detections
made anonymity depend on the detector succeeding, and it misses constantly — a hand
across the face, someone turned away, poor light. One miss is an identifiable worker in
a document sent to a client, so it fails closed.

One phone covers one zone — roughly 6–7 metres of width at typical mounting distance.
This is not site-wide surveillance; it is a movable monitor for the highest-risk area.

## Files

| File | What |
|---|---|
| `index.html` | The entire application — one self-contained file |
| `deck.html` | Pitch deck; print to PDF as A4 landscape |

## Pre-existing components

TensorFlow.js and the COCO-SSD pretrained model, both open source (Apache 2.0).
Everything else — rules engine, tracker, prediction, report generation, UI — is ours.

## Licence

MIT
