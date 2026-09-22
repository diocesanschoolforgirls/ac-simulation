# AC Circuits: Reactance, Impedance and Resonance

An interactive learning resource and simulation for **NCEA Level 3 Physics, AS91526 (Electrical Systems)**,
covering the alternating current half of the standard.

**Live:** https://vcanela.github.io/ac-simulation/

One self-contained HTML file. No build step, no dependencies, no installation. Open it from a USB stick,
a school network share, or the web address above, and it works the same.

## What it covers

| Tab | Content |
|---|---|
| 1. AC and rms | Resistor on AC, voltage and current in phase, why the power curve never goes negative, r.m.s. as "the DC that would heat it equally" |
| 2. One component at a time | R, C and L separately: rotating phasors linked to the waveforms, the physical mechanism behind each phase shift, and the reactance against frequency curve |
| 3. The mechanical twin | The series LCR circuit as a driven mass on a spring with friction, both animations driven by the same sliders |
| 4. The LCR bench | The full simulation: animated circuit, four voltage traces, live Kirchhoff check, phasor diagram with the addition construction, impedance triangle |
| 5. Resonance | Current against frequency with an auto sweep, phase against frequency, the two reactances crossing at f₀, and the V_L / V_C overshoot |
| 6. Check yourself | Exam-style questions with randomised numbers and full reasoning |

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

## Notes for teaching

- Animation runs in scaled time. The phase advances at a fixed visual rate whatever the circuit frequency
  is, so the waves stay readable at 5 Hz and at 5 kHz. The graph time axis still carries the real
  millisecond values, so raising the frequency shows as a shorter period on the axis.
- Values shared across tabs 2 to 5, so a circuit set up on one tab carries over to the next.
- Dark and light themes, remembered between visits. Light is usually better on a projector in a lit room.
- Z = √(R² + (X_L − X_C)²) is not on the NCEA formula sheet. The page says so where it matters.

## Licence

Free to use and adapt for teaching.
