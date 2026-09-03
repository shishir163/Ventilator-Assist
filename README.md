# VentAssist — ICU Ventilator Companion (PWA)

A single, offline-capable web app for the ICU round:
- **Calculator** — compliance, driving pressure, resistance, MV, P/F, BMI + PBW, with plain-language interpretation and an obesity prompt.
- **Setup Wizard** — fresh intubation? Enter height/sex and the picture (ARDS, COPD, neuro, metabolic, obese, normal) → starting VT/RR/PEEP/FiO₂/I:E.
- **Infusion Calculator** — interactive mL/hr for sedatives/analgesics, muscle relaxants and inotropes/vasoactives. Enter vial amount, dilution volume, weight and target dose; the dose range sits alongside and out-of-range doses are flagged. (Math verified against 8 clinical examples.)
- **Waveform Quiz** — see the trace, name the problem, with explanations; great for teaching on the round.
- **ABG Interpreter** — full step-by-step acid–base: primary disorder, Winter's / compensation formulas, anion gap (+albumin correction), delta ratio, and A–a gradient, each explained in words. (Concept based on Dr. Abdullah Al Mamun Shishir's reference chart.)
- **I:E & Timing Lab** — live Ti/Te/ratio/cycle.
- **Waveform Cheat-Code** — 14 tappable scalar *and* loop patterns (P–V and F–V loops included).
- **Disease Strategy** — 13 conditions incl. ARDS, COPD/asthma, ILD, both pneumothorax states, oedema, neuro (ICP/tumour/stroke), the acidoses, and a dedicated **Obesity** card.
- **Weaning** — readiness checklist + RSBI + the **RASS** sedation scale with the weaning target highlighted.
- **Trends** — save a reading per patient (bed label) and watch **compliance** and **driving pressure** plotted over time, with target bands. Stored locally on the device.
- **PEEP / FiO₂ table** — ARDSnet lower- and higher-PEEP ladders; enter FiO₂ and the matching PEEP band is highlighted.
- **Learn & Notes** — the core ventilator theory as colourful, tappable cards: loop vs scalar, how to read the P–V and F–V loops, disease patterns, compliance/driving-pressure formulas, how to measure correctly, DOPES, and the 10-second bedside routine.
- **Share** — from the Calculator, one tap builds a clean patient summary (settings + measured + computed + plan) and opens the phone's share sheet (or copies to clipboard).
- **Troubleshoot** — DOPES + high/low pressure algorithms.
- **Quick Reference** — vent + ABG normal values and formulas.

English ⇄ বাংলা toggle. Works on desktop and mobile; installs to the home
screen with its own logo.

> **Clinical note:** decision-support only. Every suggestion needs your own
> judgement and a look at the patient. Targets follow ARDSnet / standard
> guidelines. Confirm plateau on a passive patient and rule out auto-PEEP
> with an expiratory hold before acting on any number.

## Files
- `index.html` — the whole app (UI + all clinical logic, one file)
- `manifest.json` — makes it installable with name/logo/colours
- `sw.js` — service worker for offline use
- `icon-192.png`, `icon-512.png`, `icon-512-maskable.png` — app icons

## Try it locally
Just open `index.html` in a browser to see everything. (The install prompt
and offline caching only activate when served over http/https, not from a
`file://` path — see below.)

## Put it online (free) — GitHub Pages
1. Create a new GitHub repository, e.g. `vent-assist`.
2. Upload all the files in this folder to the repo root.
3. Repo **Settings → Pages → Source: Deploy from a branch → main / root → Save.**
4. In a minute you'll get a URL like `https://<yourname>.github.io/vent-assist/`.
5. Open that URL on your phone.

## Install on a phone (home-screen app)
- **Android / Chrome:** open the URL → menu (⋮) → **Add to Home screen** /
  **Install app**. The VentAssist logo appears on your home screen and it
  opens full-screen, offline.
- **iPhone / Safari:** open the URL → Share → **Add to Home Screen.**

## Roadmap ideas for v2
- Save a patient's numbers and chart the compliance / driving-pressure trend
  across shifts.
- Multi-patient list.
- ABG interpreter (full acid–base + expected compensation).
- PEEP/FiO₂ table (low- and high-PEEP ARDSnet) built in.
- Printable one-tap summary of the current patient's settings + plan.
- Editable local notes per module.
