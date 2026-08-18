# Analogplotter — The Big Update

The film curve analyzer has been rebuilt from the ground up — new name, new interface, verified math, and a set of features that make testing film genuinely more pleasant. Here's everything that changed.

## The math is now verified against the primary literature

Every core formula was checked line by line against the original sources — ISO 6:1993, Nelson & Simonds (1956), the Kodak Contrast Index papers (Niederpruem/Nelson/Yule 1966), Jones & Condit (1941), and Todd & Zakia (1964). Most of it was already correct. Two real errors were found and fixed:

- **Fractional Gradient (Jones) speeds** now average the gradient over **1.5 log H** as Nelson & Simonds define it (previously 1.3 was used — Jones EIs were slightly overestimated, most on long-toe films).
- **The default fixed flare value is now 0.40 log H** (previously 0.80 — double what any published source supports). It remains fully adjustable.

Also clarified: per ISO 6, a true **ISO speed** only exists at ΔD = 0.80. The tool now labels everything else correctly as an effective speed (EFS/EI), both on screen and in PDF reports.

## Your data is safe now

- **Everything survives a reload.** Curves, paper grades, and settings auto-save as you type and restore when you come back. No more losing an hour of densitometer readings to an accidental refresh.
- **Undo for deletions.** Removed a curve by mistake? An Undo button appears for a few seconds and brings it back exactly as it was.
- **Imports can't destroy your work anymore.** Importing a wrong file used to silently wipe existing paper curves — files are now validated first.
- **Saved sessions round-trip faithfully.** Smoothing settings and your chosen reference curve are now included in JSON exports, so a re-imported session produces identical results.

## Easier data entry

- **Paste from anywhere.** Density fields accept commas, semicolons, tabs, spaces, or newlines — straight from a spreadsheet column if you like.
- **Live value counter** under every data field, which turns red and tells you the expected count when your readings don't match your step definition.
- **Hover readout on the curve chart** — move the mouse across the plot and read log H plus the interpolated density of every curve at that point.
- **Typing is smoother** with recalculation now debounced.

## A completely new interface

- The tool is now called **Analogplotter**, with a proper wordmark and a clean, modern design: full-desktop layout, one slim header with tabs (now with icons), and a coordinate system that fills your screen as the centerpiece.
- **Each tab is its own workspace.** Curves shows the film sections and result tables; Tone Reproduction has its settings on the left and the quadrant readouts as fold-out panels beside the diagram; Analysis Plots is pure full-width plots; Paper Curve mirrors the film workflow exactly — including reordering grades with arrows.
- **Sidebar sections fold** and the settings column stays pinned to your screen — no more scrolling around to find a control.
- **First-visit guide.** New users get a short illustrated introduction — absolute vs. relative testing, how to run a development series, and how the three speed criteria differ — with a one-click **example dataset** (a realistic 4-time development series) to explore before entering their own data.

## The Jones diagram grew up

- The four-quadrant tone reproduction diagram is now a true square, larger, and decluttered — all text readouts moved into panels beside it.
- A long-standing rendering bug was found and fixed: the dashed construction lines **now meet exactly** at the quadrant seams (a chart-library layout quirk had been shifting one quadrant by a few pixels).
- Axis ranges hug your actual data, so the curves fill the quadrants instead of floating in empty space.

## Better PDF reports

- **Sharper curves**: chart images render at 3× resolution as lossless PNG.
- **Smaller files**: the tone-reproduction pages — previously several MB each — are now compact, and the whole document is compressed.
- Cleaner, lighter table styling throughout, plus fixes for charts running off the page and a footnote that never printed.

## And dozens of smaller fixes

Crash fixes in the film-comparison export, memory leaks removed, color pickers that look like color chips instead of framed rectangles, buttons that stay put when you switch tabs, curve names with special characters no longer breaking the layout — and much more.

Enjoy the tool and happy experimenting!
