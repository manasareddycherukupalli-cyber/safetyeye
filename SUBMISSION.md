# iQOO Hackathon 2026 — Bengaluru City Battle
## Team Fight Club · Open Innovation · Student bucket
## Submission copy — paste in this order

Dashboard: https://iqoo.reskilll.com/dashboard/iqoo-bengaluru
Only the team leader (Surendra) can submit.

---

## 1. IDEA TITLE

SafetyEye

---

## 2. DESCRIPTION

SafetyEye turns any phone into an offline workplace-safety monitor for small
construction sites, factories and warehouses — the places that can never justify a
₹2 lakh CCTV-and-server installation, and so have no monitoring at all.

Prop the phone facing a hazard, draw a danger zone and a fire exit on the live camera
with your finger, and set a safe headcount. An open-source vision model (COCO-SSD on
TensorFlow.js) runs entirely on the device. No cloud, no uplink, no subscription.

Every camera-based safety system today is forensic: it documents breaches after they
happen. SafetyEye tracks how each person is moving, predicts they are about to cross
the line, and calls out a spoken warning before they do — because unlike a camera
wired to a server room, the phone is physically present and has a speaker. It only
logs a breach when the warning failed, so the shift report leads with a number no
forensic system can report: incidents prevented.

At shift end one tap produces a compliance report. People in the outgoing report are
blurred on-device while the supervisor keeps the clear frames — the supervisor sees
everything, the paperwork sees nobody. Because inference is local, worker footage
physically cannot leave the phone.

---

## 3. VIDEO WALKTHROUGH URL  (optional)

Leave blank, or record on the phone via the tunnel URL and upload to YouTube unlisted.

---

## 4. PROTOTYPE URL  (optional)

Leave blank unless deployed to a permanent host (Netlify Drop / GitHub Pages).
Do NOT use the cloudflare tunnel URL — it expires.

---

## 5. DECK / DOCUMENT  *** REQUIRED ***

File: deck.html  →  open in Chrome  →  Ctrl+P
  Destination:        Save as PDF
  Layout:             Landscape
  Margins:            None
  Background graphics: TICKED   (essential — without it you lose all colour)
Max 25 MB.

---

## 6. ANDROID PROFICIENCY

Do NOT leave on "No Android experience".
Manasa has shipped SmackCheck (cross-platform iOS/Android) and lists Android
Development as a skill. Pick the option matching "has built and shipped mobile apps".

---

## 7. LLM PROFICIENCY

Do NOT leave on "No LLM experience".
Surendra worked on the Legal AI Agent — frontend interface, backend integration, API
connectivity, an AI interaction system for legal queries.
Pick a beginner-to-intermediate option. Not the highest: his contribution was
integration, not model work.

---

## 8. PRIOR BUILDS & HACKATHONS

Surendra Avula — B.Tech Mechanical Engineering, Alliance University (2025–29).
Freelance frontend developer for ~1 year, at Couture Services Pvt Ltd and independently.
Next.js, React.js, JavaScript, HTML/CSS, Git.
· Legal AI Agent — frontend interface and backend integration for an AI system handling
  legal queries; API connectivity and data flow handling.
· Rise with Jeet — frontend components for a UPSC preparation platform; layout
  structure, UI consistency, navigation.
· Carry On — frontend features, responsive pages, UI-to-backend integration.
· PMG, CBO, POS System — UI implementation, feature integration, billing workflow
  usability, component structure.

Manasa Reddy — B.Tech Computer Science, Alliance University. Freelance app developer at
Globonexo International and Couture Services Pvt Ltd, ~10 months each.
· SmackCheck — shipped a cross-platform iOS/Android food rating app with a team of
  three: frontend, backend services, database integration, authentication, review
  management.
· RiseWithJeet — backend architect: API design, database structure, authentication
  systems, server-side performance.
· Microsoft Power Platform — business applications and workflow automation with Power
  Apps and Power Automate.
· CarryOn — functional, usability and regression testing; documented test cases.

Shipped together: we have both worked on Rise with Jeet and Carry On at Couture
Services — Surendra on frontend, Manasa on backend and QA.

Hackathons: Bharatiya Antariksh Hackathon 2026 — presented by the Indian Space
Research Organisation (ISRO), powered by Hack2skill. Both of us participated and
completed a successful idea submission (Aug 2026; certificate IDs 2026H2S06BAH-P31519
and 2026H2S06BAH-P31517).

---

## 9. WHAT MAKES YOU AND YOUR TEAM STAND OUT?

We are a frontend/backend pair who have already shipped products together. At Couture
Services, Surendra built the frontend and Manasa built the backend on Rise with Jeet
and Carry On. We are not forming a team for this hackathon — we are bringing one that
already works, with a division of labour we have used on real deliverables.

The stack is our daily work. SafetyEye is JavaScript running in the device runtime.
Surendra works in Next.js, React and JavaScript full time; Manasa has shipped
cross-platform iOS/Android apps and built production APIs, databases and auth. Nothing
in this build is unfamiliar ground for us.

And we are submitting a working prototype, not a concept. SafetyEye already runs: an
open-source detector (COCO-SSD on TensorFlow.js) executing entirely on-device, danger
zones drawn on the live camera with a finger, a tracker that predicts a breach and
speaks a warning before it happens, a persistent shift log that survives the phone
locking, and a one-tap compliance report with on-device blurring.

Why this problem: Surendra is a mechanical engineering student — machinery, factory
floors and the people working around them are the world he studies. The workplaces
with the worst safety outcomes in India are exactly the ones that can least afford the
technology that would fix them. That inversion is what we wanted to attack.

Why this build fits this format: we deliberately chose an architecture we can build ON
the phone during Red Light — a self-contained web build we can edit and run on the
device itself — rather than a native app that would strand us without a laptop for
eleven hours. And the product's central claim, that footage physically cannot leave
the device, is a property of that architecture rather than a policy we wrote down.

---

## 10. CONFIRMATION CHECKBOX

Tick: "I confirm this idea is our team's original work and any pre-existing
components are disclosed."

Pre-existing components to be aware of if asked: TensorFlow.js and the COCO-SSD
pretrained model (both open source, Apache 2.0). Everything else — the rules engine,
tracker, prediction, report generation, UI — is ours.

---

## 11. SUBMIT IDEA

---

# NOTES

- Deadline: idea submission. City Battle is Bengaluru, Aug 29–30 2026.
- Judging at the event (not this form): End product quality 30% · Novelty and impact
  20% · HackTracker creative phone use 15% · Technical depth 15% · HackTracker Office
  Kit usage 10% · Demo and presentation 10%. 75% jury, 25% device telemetry.
- Office Kit is the phone-to-laptop bridge (screen mirror, clipboard, file transfer,
  remote control) — NOT a document suite. Its 10% is measured from device data during
  the build weekend. Do not claim the .doc export is "Office Kit integration".
- Local files: index.html (the app), deck.html (the deck), SUBMISSION.md (this file).
