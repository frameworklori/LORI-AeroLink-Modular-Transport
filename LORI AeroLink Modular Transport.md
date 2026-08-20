<!--
LORI AeroLink Modular Transport
Coupler Engineering Development Record
Record Date: 2026-08-20
Status: Research-stage / preliminary structural concept / pre-FEA / pre-prototype
-->

LORI AeroLink Modular Transport

Coupler Engineering Development Record

Lori-framework Original Design | Research-Stage Engineering Record
Record Date: August 20, 2026 | Revision: Integration Record 01

1. Purpose of This Record

This document preserves the engineering evolution of the LORI AeroLink modular transport coupling concept as discussed and iteratively reviewed on August 20, 2026. It integrates the original Lori-framework concept, Claude's preliminary engineering calculations and architecture split, and the subsequent review conclusions. The purpose is documentation and traceability, not certification. Numerical outputs remain preliminary hand-calculation targets unless independently validated.

2. Original AeroLink Coupling Concept

The original AeroLink concept proposed a streamlined front vehicle platform with interchangeable rear modules such as a VAN, cargo module, open cargo bed, or other transport body. The early visual concept used a strong magnetic detachable connection inspired by the rapid coupling philosophy of high-speed rail. Engineering review subsequently refined the role of magnetism.

Magnetism should not be credited as the primary structural load path.

Magnetic or electromagnetic elements are retained for alignment, approach guidance, and light preload.

A positive mechanical lock (pins/collar/cam mechanism) carries structural loads.

A separate blind-mate utility interface carries electrical power, control, braking, lighting, data, and diagnostics as applicable.

3. Hybrid Auto-Coupler Interface

The refined interface is organized into three independently engineered functional zones:

Zone

Function

Engineering role

Outer ring

Magnetic alignment

Guides the two faces into alignment and may provide light preload. Magnets are not credited as part of the certified structural load path.

Mid ring

Mechanical structural lock

Positive pins/collar/cam structure carries the required structural loads. Loss of magnetic force must not release the joint.

Center

Utility blind-mate

Spring-compliant, structurally isolated interface for low-voltage power, safety/control, data, and optional higher-power services subject to dedicated interlocks.

Proposed mating sequence: magnetic alignment -> position confirmation -> mechanical lock engagement -> utility connector seating. Detachment reverses the sequence so the utility connector is not separated while the structural interface remains loaded.

4. Why the First Calculation Model Was Rejected

The first calculator mixed translational reactions from a free-pivot joint with rotational moments from a rigid collar in the same load case. Those are different boundary conditions and therefore did not form one internally consistent free-body model. The calculation was useful as a screening exercise, but the mixed model was explicitly retired rather than treated as a final engineering result.

5. Revision B - Two Independent Boundary Architectures

Claude's Revision B separates the problem into two non-mixed architectures. Each architecture has its own reaction degrees of freedom, equations, and per-load-case pin sizing. The governing case is selected only after each physical load case is evaluated.

5.1 Architecture A - Articulated Trailer-Type Coupling

Architecture A is an idealized three-axis rotationally free coupling. The rear module carries its own weight through its axle(s). Under this explicit idealization, the coupling transmits Fx, Fy, and Fz, while Mx = My = Mz = 0. Vertical reaction is obtained from static geometry and weight transfer; longitudinal and lateral force sharing depends on assumed tire/brake traction fractions.

Load cases: static tongue load, braking, acceleration, cornering/evasive maneuver, simplified road shock, and simultaneous braking + cornering.

Revision-B example result: governing case = combined braking + cornering.

Revision-B example hand-calculated shear-equivalent minimum pin diameter = 5.1 mm.

The 5.1 mm result is not a production design diameter; fatigue, pin bending, clearance impact, wear, corrosion, stress concentration, crash loads, tolerances, and positive-latch geometry remain outside this simple sizing result.

5.2 Architecture B - Rigid Detachable Cantilever Module

Architecture B represents the opposite boundary case: the rear module has no supporting axle and is carried entirely at coupling point C as a rigid cantilever. The coupling therefore reacts all six components Fx, Fy, Fz, Mx, My, and Mz. In this idealized model, weight and inertial forces generate direct cantilever moments at C.

Revision-B example result: governing case = simplified road shock.

Revision-B example hand-calculated shear-equivalent minimum pin diameter = 49.1 mm.

The large increase relative to Architecture A illustrates the structural cost of eliminating rear axle support and forcing the collar to carry full bending/torsion.

Road-shock values are empirical screening bounds based on a dynamic load factor, not first-principles transient dynamics.

6. Per-Case Pin/Collar Sizing Method

Revision B no longer creates a synthetic vector by independently taking the maximum of every force and moment axis. Instead, each real load case is converted into a pin design load, and the largest physical case becomes the governing case.

For Architecture A, only direct translational force enters the preliminary pin shear calculation. For Architecture B, direct force plus torsional and bending contributions are converted to pin-circle forces. The method uses a conservative linear sum for preliminary screening.

Material strength is user-editable. Alloy presets may populate example allowable shear and bearing stresses, but the values must be replaced by certified properties for the actual material condition, heat treatment, geometry, and supplier specification before engineering design.

7. Important Interpretation of Architecture A vs. B

Architecture A and Architecture B should be treated as boundary cases, not automatically as the final AeroLink configuration. Architecture A minimizes transmitted moment by allowing articulation and retaining axle support. Architecture B removes axle support but imposes very large structural demands on the detachable interface.

8. Proposed Next Architecture - Architecture C

The original AeroLink VAN/cargo concept may be better represented by a third architecture: a wheeled rear module with a rigid or semi-rigid detachable structural interface. The rear axle would support substantial vertical load, while the coupling would have finite pitch/yaw/roll stiffness rather than the zero-stiffness limit of Architecture A or the no-axle cantilever condition of Architecture B.

Architecture C is expected to be statically indeterminate once coupling rotational stiffness, suspension stiffness, chassis torsional stiffness, module-frame stiffness, axle compliance, bushings, and tire stiffness all participate in load sharing. Statics alone should not be used to fabricate a unique moment split. A stiffness-matrix model, finite-element analysis, and/or multibody vehicle dynamics model would be required.

A useful future research requirement is that the Architecture-C model behave consistently with its limiting cases: as coupling rotational stiffness becomes very small it should approach articulated behavior; as interface stiffness becomes very large, moment transfer should increase toward rigid-module behavior, subject to the continuing support of the rear axle.

9. Electrical / Data / Brake Interface Development

The coupling concept must include a utility interface rather than only mechanical and magnetic elements. Safety-critical functions should not be casually assigned to a generic wireless link or undifferentiated pogo-pin array.

Low-voltage auxiliary power.

Safety-critical braking/control signals with appropriate redundancy.

Lighting and module identification.

CAN and/or automotive Ethernet data.

Optional high-voltage power using interlock, pilot contact, pre-charge, contactor sequencing, and touch-safe connector design.

Optional pneumatic services if required by the selected vehicle class.

10. What Is Hand-Calculable vs. What Requires Validation

Preliminary / screening calculations

Requires FEA, dynamics, test, or regulatory work

Static equilibrium and tongue-load estimates under explicit geometry assumptions

Combined multiaxial pin/collar stress and local stress concentration

Per-case translational reactions for the idealized articulated model

Fatigue, fretting, wear, corrosion, tolerances, and latch durability

Exact rigid-body cantilever reactions for the idealized no-axle model

Crash and abuse loads

Preliminary pin shear/bearing screening

Trailer sway and full vehicle multibody dynamics

Simplified road-shock DLF estimate (screening only)

Architecture-C stiffness/load sharing



Connector vibration, ingress, mating-cycle and HV qualification



Jurisdiction-specific road-vehicle homologation and coupling regulations

11. Current Engineering Position - 2026-08-20

The AeroLink coupling concept is retained, but its engineering interpretation has changed materially. The project no longer assumes that strong magnets alone should carry road-vehicle structural loads. The preferred conceptual direction is magnetic-assisted alignment + positive mechanical structural locking + isolated utility blind-mate connections.

Architecture A and B are retained as useful boundary models. Architecture C is identified as the most relevant next research branch for a rear module that remains wheel-supported but becomes structurally integrated with the front platform after coupling.

12. Attribution, Status, and Record Notice

Project: LORI AeroLink Modular Transport
Framework / Concept Attribution: Lori-framework Original Design
Engineering discussion integrated from: Lori-framework concept development, Claude preliminary engineering analysis/calculator, and subsequent model review
Record date: August 20, 2026
Status: Research-stage / preliminary structural concept / pre-FEA / pre-prototype

This record documents the development path and assumptions as of the stated date. It does not claim that every individual technology is novel, patentable, or unprecedented, and it does not certify roadworthiness or manufacturing readiness. Future revisions should be added as new dated versions rather than deleting this record.

Appendix A - Revision-B Example Values Preserved for Traceability

Architecture

Governing case

Example minimum pin result

Interpretation

A - Articulated

Combined braking + cornering

5.1 mm

Hand-calculated shear-equivalent screening minimum; not a design diameter.

B - Rigid cantilever

Simplified road shock

49.1 mm

Shows structural penalty of carrying the module entirely at the coupling; not a certified design diameter.
