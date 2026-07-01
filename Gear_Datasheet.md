# Spur Gear — Design & Material Selection Datasheet
**Task 1: 3D CAD Model Creation** · Component: Involute spur gear (pinion) with integral hub · Drawing No. ME-T1-001

---

## 1. Component description
A 24-tooth involute spur gear with a central bore, single keyway, and an integral extended hub. The part transmits rotary motion and torque between parallel shafts. Geometry follows the ISO 53 basic rack (20° full-depth involute), so it meshes with any standard module-2 spur gear.

## 2. Geometric specification

| Parameter | Symbol | Value |
|---|---|---|
| Module | m | 2 mm |
| Number of teeth | z | 24 |
| Pressure angle | α | 20° |
| Pitch circle diameter | d = m·z | 48.0 mm |
| Base circle diameter | d·cos α | 45.105 mm |
| Outside (tip) diameter | d + 2m | 52.0 mm |
| Root diameter | d − 2.5m | 43.0 mm |
| Addendum / dedendum | a / b_f | 2.0 / 2.5 mm |
| Circular pitch | p = πm | 6.283 mm |
| Tooth thickness (pitch) | s = p/2 | 3.142 mm |
| Face width | b | 20 mm (= 10·m, within 9–13·m guideline) |
| Bore | — | Ø16 H7 |
| Hub diameter / projection | — | Ø30 / 12 mm |
| Keyway (DIN 6885, key 5×5) | — | 5.0 wide × 2.3 deep |
| Overall axial length | — | 32 mm |

Model volume (from solid) ≈ **36.7 cm³**.

## 3. Material selection

**Selected material: AISI 4140 (DIN 42CrMo4) alloy steel, quenched & tempered.**

### Why this material
Gear teeth fail primarily by (a) tooth-root **bending fatigue** and (b) flank **contact/pitting fatigue**. The material therefore needs high fatigue strength, good hardenability, and toughness to resist shock loads. AISI 4140 is the standard general-purpose choice that balances all of these and is widely available and machinable.

| Property | Value (Q&T, ~28–32 HRC) |
|---|---|
| Density, ρ | 7.85 g/cm³ |
| Young's modulus, E | 205 GPa |
| Poisson's ratio, ν | 0.29 |
| Yield strength, σ_y | ≈ 655 MPa |
| Tensile strength, σ_u | ≈ 1020 MPa |
| Elongation | ≈ 16 % |
| Hardness | 28–32 HRC (core) |

**Estimated mass** = ρ × V = 7.85 g/cm³ × 36.7 cm³ ≈ **0.29 kg**.

### Heat treatment / finishing
- Through quench & temper to 28–32 HRC for the body (toughness + fatigue strength).
- Optional induction or flame hardening of the tooth flanks to 52–56 HRC for higher pitting resistance while keeping a tough core.
- Tooth flanks finish-ground after heat treatment to ISO grade ~6–7 for quiet, accurate running.

### Alternatives considered
| Material | Note |
|---|---|
| **20MnCr5 (case-hardening)** | Best contact-fatigue life via carburising (58–62 HRC case); preferred for high-load, high-speed gearboxes. Heavier process cost. |
| **C45 / AISI 1045 (carbon steel)** | Cheaper, easy to machine; lower fatigue strength — fine for light/low-speed duty. |
| **Cast iron / polymer (POM, nylon)** | Quiet, self-lubricating, low load only; not for sustained torque. |

AISI 4140 was chosen as the best all-round balance of strength, toughness, cost, and manufacturability for a general power-transmission gear.

## 4. First-order load capacity (Lewis bending, indicative)

Lewis equation: **W_t = σ_allow · b · m · Y**

Assumptions: Lewis form factor Y ≈ 0.337 (z = 24, 20° full-depth); allowable bending stress σ_allow ≈ 200 MPa (4140 Q&T with fatigue + safety-factor derating).

- Allowable tangential tooth load **W_t ≈ 200 × 20 × 2 × 0.337 ≈ 2.7 kN**
- Transmissible torque **T = W_t · d/2 ≈ 2700 × 0.024 ≈ 65 N·m**
- Indicative power at 1500 rpm **P = T·ω ≈ 65 × 157 ≈ 10 kW**

> These are preliminary hand-calculation figures to confirm the geometry is sensibly sized. A production design would verify against AGMA 2001 / ISO 6336 (bending + contact), including application, dynamic, size, and load-distribution factors, plus a contact-stress (pitting) check.

## 5. Deliverable files
| File | Purpose |
|---|---|
| `spur_gear.step` | **Primary CAD model** — opens in SolidWorks, Creo, AutoCAD, Fusion 360, Inventor, etc. |
| `spur_gear.stl` | Mesh for 3D printing / quick viewing |
| `spur_gear_profile.dxf` | 2D tooth profile for laser/wire-EDM or import |
| `drawing_sheet.pdf` | Dimensioned engineering drawing (front view + section + data) |
| `render_*.png` | Rendered images of the model |
