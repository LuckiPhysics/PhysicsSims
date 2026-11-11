# Instructions for AP Physics 1 mini-lessons (PhysicsSims)

This repo is published with GitHub Pages at https://luckiphysics.github.io/PhysicsSims/ (repo: LuckiPhysics/PhysicsSims).
Every flipped-classroom unit follows the format set by `ap1/momentum/ml1-momentum.html`. Use that file as the reference.

## Ground rules
- **Never change an existing file without asking first.** Adding new files is fine.
- Put each unit's files in `ap1/<unit>/` (for example, `ap1/momentum/`). Name files `ml<N>-<topic>.html` and `ml<N>-<topic>-notes.pdf`.
- Answer keys and anything with answers for the teacher go in the unit's materials folder, **not** in this repo, because the site is public.
- Build from the teacher's materials in this order: slides first, then the CED for anything the slides skip. Use the binder pages for lab names and practice problems.
- Plan the whole unit before building: a day-by-day map with which days get a mini-lesson, what each one covers, and a 5-minute opener for the next class. No mini-lesson is due on a lab or test day. Stop for the teacher's review after the map and after the first prototype.

## Mini-lesson requirements
- **Self-contained HTML.** No outside libraries, fonts, CDNs, or images. Inline all CSS and JS, and draw diagrams as inline SVG.
- **iPad-first.** Students use school iPads, not laptops.
  - Tap targets at least 48px tall, and main buttons 56px.
  - Say "tap," never "click."
  - Must work in portrait, with no sideways scrolling.
  - Body text at least 18px, single column, max width about 720px.
  - The iPad number pad has no minus key, so give numeric answers a big ± toggle button next to the input.
  - Use `touch-action: manipulation` on buttons, and respect `env(safe-area-inset-bottom)`.
- **Light and dark mode.** Follow the system setting, plus a Theme button that cycles Auto / Light / Dark. The localStorage read/write must be wrapped in try/catch.
- **Length:** 10–15 minutes, in short chunks, one per screen, with a progress bar and fixed Back / Next buttons at the bottom.
- **Structure:**
  1. A start screen where the student types their name (required to start), with the due date and a "have your notes sheet out" reminder.
  2. 3–4 concept chunks. Each chunk has an orange "Notes · Box X" tag that matches a box on the guided-notes sheet. Include at least one interactive piece, such as a slider or a tap-to-reveal step.
  3. One worked example, taken from the teacher's slides, shown one step at a time ("Tap to show the next step").
  4. 2–3 check questions, one per screen.
     - Give instant feedback. Wrong-answer feedback targets the specific mistake, such as a sign error.
     - Students get up to 3 tries before moving on.
     - Record first-try results.
  5. A results card for students to screenshot. It shows:
     - name, date and time, and the lesson title
     - first-try score
     - each question marked "first try," "after N tries," or "review in class"
     - a "notes sheet done" self-check
     - an optional "still unsure about" note
     - a short check code
     Put the iPad screenshot instructions above the card: top button + volume up, or top button + Home on older iPads. Students turn screenshots in on **OnCampus**.
- **Look:** match the site's slate/blue palette, with blue accents and amber for notes tags.
- **Back link:** put a "← Unit N: Name" link at the top that goes to the unit page (`index.html` in the same folder).
- **Teacher view:** every mini-lesson supports `?teacher` at the end of its URL (copy the block from `ml1-momentum.html`). It shows:
  - all parts on one page, labeled "Part N of M"
  - every tap-to-reveal step opened
  - correct answers highlighted, with the feedback students get for each wrong answer
  - a sample results card
  - no bottom nav and no gating
  - a `noindex` tag
  List each lesson on the unlisted `teacher/index.html`, with Teacher view, Student view, and Notes PDF buttons. Never link to the teacher page from student pages. The site is public, so treat it as unlisted, not private.

## Guided-notes PDF requirements
- One page, letter size, printable, with matching boxes A, B, C, and so on, in the same order as the lesson's notes tags.
- Diagrams are already drawn, so students fill in key ideas in blanks instead of copying slides.
- Each box's diagram must be the same kind of picture as the lesson part with that tag. If the lesson shows a force bar, the box shows a force bar, not a graph that a later lesson introduces. Before shipping, compare every box with its lesson part.
- A work space for each check question, plus a "Big idea in one sentence" line.
- A QR code in the header that opens the lesson on the iPad camera. Decode it to confirm the address is correct.
- Also make an answer-key version (blanks filled in), saved outside this repo.

## Before handing off
- Test in Playwright with an iPad device profile in both light and dark mode: walk through every step, check that there are no console errors, and check that there is no horizontal scroll.
- Render the notes PDF and look at it, and confirm it's exactly one page.
- **Site layout.** The hub's Physics button opens `index.html`, which links to three sections:
  - `simulations/index.html` lists the sims. The sim files themselves stay at the repo root so old links keep working.
  - `ap1/index.html` has AP Physics 1 unit cards. Each live unit has its own page, such as `ap1/momentum/index.html`, listing that unit's mini-lessons with "Start lesson" and "Notes sheet (PDF)" buttons.
  - `honors/index.html` has Honors Physics unit cards (Energy, Circuits, Forces, Motion, Waves). Live units have pages such as `honors/circuits/index.html`.
- **When a new mini-lesson is ready,** turn on its card on the unit page by replacing "Opens soon" with the two buttons. When a new unit starts, turn on its card on the course page and create its unit page in the same style. These pages share the same inline CSS, so copy it from an existing page.
- Updating these listing pages is expected when adding lessons. Any other change to existing files still needs the teacher's OK first.
- Tell the teacher what to push in GitHub Desktop (Commit to main, then Push origin).
