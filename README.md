# Analog Film Curve Analyzer

A single-file, browser-based sensitometry tool for black-and-white film testing. Open `index.html` in a browser — no build step, no server.

## Features

- **H&D characteristic curves** from step-wedge densitometer readings (auto 0.15 steps, custom log H, step-tablet, or absolute lux-seconds)
- **Contrast metrics**: Contrast Index (Kodak concentric-arc method), gamma, G-bar
- **Film speed**: fixed density (ISO 6, S = 0.8/Hm), Delta-X criterion (Nelson & Simonds 1956), fractional gradient (Jones 0.3Ḡ), plus a synthetic interpolated ΔD = 0.80 curve per ISO 6:1993 Annex A
- **Exposure planning**: LSLR/SBR from fixed or dynamic ("practical") flare models, development aims table (N−2 … N+3), scene LSLR lookup
- **Paper curves**: measured paper grades with LER/ISO(R), grade interpolation, CMY filtration hints
- **Tone reproduction**: full four-quadrant Jones diagram using measured film and paper data
- **Import/Export**: JSON sessions, paper-only JSON, BTZS `.pfc` files, PDF reports, multi-film comparison PDF

## Formula sources

Calculations verified against the primary literature: ISO 6:1993, Nelson & Simonds (JOSA 46, 1956), Niederpruem/Nelson/Yule (PS&E 10, 1966), Todd & Zakia (PS&E 8, 1964), Jones & Condit (1941), and the "What is Normal" developmental model (fixed flare 0.40, LER 1.05, normal LSLR 2.20, CI 0.58).

Note: per ISO 6:1993 a true ISO speed exists only at ΔD = 0.80; all per-development values reported by the tool are effective speeds (EFS/EI).

## Dependencies

Loaded from CDNs at runtime (internet required): Tailwind CSS, Chart.js, jsPDF, html2canvas.
