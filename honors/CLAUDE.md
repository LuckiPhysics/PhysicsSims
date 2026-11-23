# Instructions for Honors Physics mini-lessons (PhysicsSims/honors)

Follow `../CLAUDE.md` for everything: ground rules, iPad-first build, look, `?teacher` view, notes PDFs, testing, and site layout. This file only lists what is different for Honors (freshman Honors Physics, loosely AMTA modeling).

## Honors format vs. AP
- Light math. Shorter: about 8–10 minutes.
- Include the name screen and results card. Whether students turn it in on OnCampus is the teacher's call. (The AP Energy review set has no results card. Add it back when porting.)
- Keep the guided-notes PDF and the `?teacher` view.
- Files go in `honors/<unit>/` (for example `honors/energy/`). Back link: "← Energy" to `index.html` in the same folder. Kicker: "Honors Physics · Energy".

## Energy notation and diagrams (Honors)
- **Use E with a subscript for every form. Never U or K.**
  - E<sub>k</sub> kinetic
  - E<sub>g</sub> gravitational
  - E<sub>el</sub> **elastic** (never "spring energy")
  - E<sub>dis</sub> dissipated (thermal energy is lumped in here; don't use E<sub>th</sub>)
- **Don't use "open" or "closed" systems.** Either students define the system, or the problem defines it for them. If something **outside** the system does work on it, draw an **arrow into** the system (energy in, +W) or **out of** it (energy out, −W). No arrow means nothing outside does work.
- **LOL diagrams.** L = initial bar chart · O = a circle for the system, listing every object inside it, with work arrows crossing the circle · L = final bar chart. Use this in place of AP's "W<sub>ext</sub>" bar column.

## Porting the AP Energy review lessons to Honors
The AP lesson `ap1/energy/ml1-systems-bar-charts.html` (R1: Systems and Bar Charts) is approved and almost ready for Honors. Its build sources are in the private `teaching-materials/Energy materials/build/` folder (`r1-body.html`, `r1-extra.css`, `notes_r1.py`). Copy them and change only the following:

1. **Notation.** In `chart()`, change the `LAB` map to E<sub>k</sub>, E<sub>g</sub>, E<sub>el</sub>, E<sub>dis</sub>. Replace every U<sub>g</sub>, U<sub>s</sub>, K, E<sub>th</sub> and "spring energy" in the text, feedback, `?teacher` notes and notes sheet.
2. **Chart → LOL.** Replace the middle W<sub>ext</sub> bar column with the "O": a circle listing the system's objects (pass them in, e.g. `sys: ["ball", "Earth"]`). Draw the work as an arrow into the circle (w > 0) or out of it (w < 0), labeled W, with no bar.
3. **Part 3 "Open or closed?"** → **"Is anything outside doing work?"** Practice taps become *arrow in / arrow out / no arrow*. Delete the E<sub>i</sub> = E<sub>f</sub> vs. E<sub>i</sub> + W<sub>ext</sub> = E<sub>f</sub> table. Keep the idea "energy only crosses the system boundary as work."
4. **Part 2 (choosing the system)** works as is. Relabel the two choices with LOL circles: "ball" vs. "ball + Earth". Ball only: arrow in from gravity. Ball + Earth: E<sub>g</sub> → E<sub>k</sub>, no arrow.
5. **Check 2** (box sliding to a stop, system = box only): rewrite the choices without open/closed. Correct answer: the floor is outside the system, so friction takes energy out, shown as an arrow out of the system.
6. **Light math.** Keep the worked example's "the chart is the equation" step, written in E notation (E<sub>k,i</sub> = E<sub>g,f</sub>). Show ½mv² = mgh only as an optional extra line. The kinetic-energy ranking check is fine as is.
7. **Length.** Trim to 8–10 minutes. For example, cut worked-example Step 5 (friction), or shorten Part 4 to one practice question.
8. **Notes sheet.** Same Boxes A–D, with LOL frames: two bar charts plus the system circle, so students write the objects and draw the arrows. Remove the open/closed line from Box A. Make a KEY too (saved in teaching-materials, not this repo).
9. **Site.** Turn on the Energy card on `honors/index.html` and create `honors/energy/index.html`, in the same style as `honors/circuits/`. List the lesson on the teacher page.

R2–R6 of the AP Energy review set can be ported the same way once they exist: the same notation swap, LOL instead of W<sub>ext</sub>, no open/closed language, and lighter math.
