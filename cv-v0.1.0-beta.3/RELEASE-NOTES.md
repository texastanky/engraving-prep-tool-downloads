# ForgeMark Color Vectorizer v0.1.0-beta.3

Corrects a wrong line interval shipped in beta.2.

## What was wrong in v0.1.0-beta.2

beta.2 shipped a line interval of **0.4-1.0 mm** and presented it as measured. It was not measured, and it was wrong:

- The plates behind the measured window are coarse **probes** - one X glyph per cell at about **2.5 lines/cm (about 4 mm)** - not filled patches.
- The research note recorded that as "1 line per cm (about 1 mm)". 1 line/cm is **10 mm**, so the conversion was out by a factor of ten.
- 0.4-1.0 mm is **10-25 lines/cm**: neither the probe hatch nor a production fill, and coarse enough to engrave stripes instead of a solid marking.

## What this build does

- **Line interval is 0.02 mm on every shipped row - 500 lines/cm**, which is the field xTool Studio actually has. It applies to the built-in tables, per-layer overrides, the Engrave Pack, the Section Pack and the SVG metadata.
- **Line interval is marked unmeasured.** It is out of the measured window, it is never flagged as outside a range, and the caveat says in words that no interval has been measured on this machine and that 0.02 mm is a production starting value.
- Speed, power, frequency, pulse and defocus keep their measured window and their out-of-window flags unchanged.
- CSV gains a **Hatch lines/cm** column and a **Line interval measured?** column; the README and the recipe panel say the same.

## Files

- `color-vectorizer-beta.zip` - the self-contained browser app.
- `SHA256SUMS.txt` - `7257978ef8b9f3f05ce85ef2277402c87eb813c53f2616c3e1b5ef4fc2354ba0  color-vectorizer-beta.zip`

Source commit is recorded in `SOURCE-COMMIT.txt` inside the zip.
