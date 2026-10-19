# AC Circuits: Reactance, Impedance and Resonance

An interactive learning resource and simulation for **NCEA Level 3 Physics, AS91526 (Electrical Systems)**,
covering the alternating current half of the standard.

**Live:** https://interactives.diocesan.school.nz/ac-simulation/ (also mirrored at https://vcanela.github.io/ac-simulation/)

`index.html` plus a vendored copy of KaTeX. No build step, no installation, no network needed at run time.
Copy the folder to a USB stick or a school share and it works exactly as it does on the web.

## What it covers

| Tab | Content |
|---|---|
| 1. AC and rms | Resistor on AC, voltage and current in phase, why the power curve never goes negative, r.m.s. as "the DC that would heat it equally" |
| 2. One component at a time | R, C and L separately: rotating phasors linked to the waveforms, the physical mechanism behind each phase shift, and the reactance against frequency curve |
| 3. The mechanical twin | The series LCR circuit as a driven mass on a spring with friction, both animations driven by the same sliders |
| 4. The LCR bench | The full simulation: animated circuit, four voltage traces, live Kirchhoff check, phasor diagram with the addition construction, impedance triangle |
| 5. Resonance | Current against frequency with an auto sweep, phase against frequency, the two reactances crossing at f₀, and the V_L / V_C overshoot |
| 6. Check yourself | Exam-style questions with randomised numbers and full reasoning |

## Using it in class

- **Deep links.** `...#1` to `...#6` opens straight on that tab, so a link in a lesson plan lands where you want it.
- **Projector link.** Append `?theme=light`, e.g. `.../?theme=light#4`. The theme toggle is also remembered per browser.
- **Scrub, do not chase.** Every animated tab has a transport bar: play/pause, a slider that scrubs through the cycle
  by hand, and three speeds. The default is slow. Freezing the cycle at one instant and reading every panel at that
  instant is the point of the whole page.
- **Shared state.** Tabs 2 to 5 read the same circuit, so a setup made on one tab carries into the next.

## The teaching ideas behind it

**Reactance is made physical, not asserted.** For the capacitor: *the current is largest when the plates are
empty, and zero when the plates are full*. For the inductor: *the induced voltage is largest when the current
is passing through zero, and zero when the current is at its peak*. Both of those events are a quarter of a
cycle apart, which is where the 90° comes from.

**The mechanical analogy is exact, not loose.** Write the loop rule and Newton's second law side by side:

    V = L di/dt + R i + (1/C) ∫i dt
    F = m dv/dt + b v +   k   ∫v dt

so current ↔ velocity, voltage ↔ force, **inductor ↔ mass**, **capacitor ↔ spring**, **resistor ↔ friction**.
Shaking a heavy mass fast is hard, which is X_L = ωL. Pushing a spring slowly gets you nowhere, which is
X_C = 1/ωC, and at zero frequency it locks solid, which is a capacitor blocking DC. Resonance is the
playground swing. This also links the standard directly to 91524 Mechanical Systems.

**Phasor addition is shown, not stated.** The LCR bench draws the construction path (along V_R, up by V_L,
down by V_C) landing exactly on the tip of the supply phasor, and checks
v_R + v_L + v_C = v numerically at every instant.

## Design notes

- **Maths is typeset with KaTeX**, vendored into `vendor/katex/` (the library, its stylesheet, and a nine font subset,
  about 450 KB). That buys proper Computer Modern with real radicals and a vinculum, so no formula has to be written
  as `sqrt(...)` with brackets. Every formula also carries a plain text fallback inside the HTML, so if the `vendor`
  folder is ever separated from the page the maths degrades to something readable rather than disappearing.
  This is the one place the project's single file rule is relaxed, and the reason is legibility of the physics.
- **Colour is Okabe-Ito**, the colourblind-safe palette: resistor orange `#E69F00`, inductor reddish purple `#CC79A7`,
  capacitor sky blue `#56B4E9`, current bluish green `#009E73`. The supply trace is plain ink so it always reads as the
  reference, and in-graph markers are ink rather than a fifth hue. No red/green or red/blue pair carries meaning
  anywhere, every trace is labelled as well as coloured, and right/wrong in the quiz uses a tick and a cross as well
  as colour.
- **Numbers are grouped for comparison.** Within a readout group every quantity shares one SI prefix, printed once in
  the group heading, so the digits can be compared directly instead of shifting between mW and W. Live values that
  change during the animation keep a fixed prefix and a fixed character width so nothing jumps.

## Notes for teaching

- Animation runs in scaled time. The phase advances at a fixed visual rate whatever the circuit frequency
  is, so the waves stay readable at 5 Hz and at 5 kHz. The graph time axis still carries the real
  millisecond values, so raising the frequency shows as a shorter period on the axis rather than a faster animation.
- On the LCR bench the component voltage traces start switched off. Add them one at a time; four overlapping
  sinusoids at once is the thing that makes students give up on the phasor diagram.
- Z = √(R² + (X_L − X_C)²) and tan φ = (X_L − X_C)/R are not on the NCEA formula sheet. The page says so where it matters.
- The 91526 "Impedance" revision handout in circulation prints the resonance formula as f = 2π√(LC), which is wrong.
  This page uses and derives f₀ = 1/(2π√(LC)).

## Licence

Free to use and adapt for teaching.
