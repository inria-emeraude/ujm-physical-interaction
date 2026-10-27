# Digital Fabrication for Musical Interfaces and Instruments

## Lecture at a glance

- **Course:** Physical Interaction Design @ UJM
- **Duration:** 2 hours
- **Audience:** Master’s students in music, sound, design, and creative technologies
- **Prerequisites:** Introductory ideas of digital musical instruments, physical interaction, and sensors
- **Format:** Illustrated lecture, examples, discussion, and a short design exercise

Digital fabrication lets instrument makers move from a digital design to a physical object using machines such as 3D printers, laser cutters, and CNC routers. This lecture introduces the main fabrication processes and the software that connects design to production. Its focus is on making musical controllers and instruments: enclosures, buttons, brackets, wearable structures, acoustic parts, and assemblies that bring sensors and electronics into a playable form.

The central idea is that fabrication is part of instrument design. Material, geometry, assembly, and surface affect how an object is held, struck, pressed, worn, repaired, and understood by a performer and audience. The class remains at an introductory level. Detailed machine operation belongs in a trained workshop with its own equipment-specific rules.

## Learning objectives

By the end of the lecture, students should be able to:

1. Distinguish additive, subtractive, and sheet-cutting processes, and give examples of each.
2. Describe the main families of 3D printing and the kinds of objects each can produce.
3. Explain the path from a CAD model to a slicer or CAM project, machine file, fabricated part, and assembled instrument.
4. Recognize the roles of CAD, vector drawing, slicer, CAM, and machine-control software.
5. Identify design constraints that matter for a physical musical interface, including fit, strength, assembly, ergonomics, and repair.
6. Choose a plausible fabrication approach for a small musical controller and explain the choice.

## Suggested two-hour plan

| Time | Section | Format |
|---|---|---|
| 0–8 min | Opening: what does fabrication add to an instrument? | Object examples and discussion |
| 8–18 min | Three ways to shape material | Additive, subtractive, and sheet-based overview |
| 18–42 min | 3D printing technologies | Process families and comparison |
| 42–54 min | CAD and design for fabrication | Geometry, assembly, and interaction |
| 54–64 min | Short break | Break |
| 64–79 min | From 3D CAD to slicer to printer | File workflow and slicer decisions |
| 79–94 min | CNC routing and CAM | Setup, toolpaths, simulation, post-processing |
| 94–108 min | Laser cutting and other sheet processes | 2D design, operation layers, assembly |
| 108–116 min | Design exercise: fabricate a musical controller | Small-group sketch |
| 116–120 min | Summary and exit question | Wrap-up |

The timing assumes a brisk survey. If students discuss each example at length, shorten the catalogue of industrial 3D printing processes and retain the CAD-to-machine workflows and design exercise.

---

## 1. Opening: what does fabrication add to an instrument? (0–8 min)

### Opening question

> What changes when a musical controller becomes a physical object?

Invite students to name an object they have used to make or control sound: a keyboard, guitar pedal, phone, game controller, drum pad, wearable, or custom digital musical instrument (DMI). Ask what makes it playable: shape, size, texture, resistance, weight, spacing, grip, visible controls, feedback, or how it sits in a room.

Digital fabrication helps make forms that are difficult, slow, or expensive to build by hand. It can produce a custom enclosure, a shaped grip, a mounting plate for sensors, a flexible prototype, or a set of linked parts. A printed box can hold electronics, but the instrument design also decides where a hand rests, how a button is found, how movement is constrained, and whether the performer can replace a broken part.

### Three roles for fabrication in this course

- **Form:** Enclosures, handles, keys, supports, wearables, and instrument bodies.
- **Function:** Mounting sensors, controlling cable paths, providing hinges or sliding parts, and setting the movement available to the performer.
- **Experience:** Weight, texture, visibility, reach, comfort, sound from the object itself, and the audience’s sense of cause and effect.

### Prompt

Show or describe a simple controller with a microcontroller, one sensor, and a button. Ask: what would a fabricated housing improve? Possible answers include secure mounting, repeatable sensor placement, comfortable grip, protection during performance, and a more legible relationship between action and sound.

---

## 2. Three ways to shape material (8–18 min)

Introduce the broad distinction between **additive**, **subtractive**, and **forming or joining** processes.

| Process family | Basic idea | Examples | Typical musical-interface use |
|---|---|---|---|
| Additive | Build an object by adding material, often in layers | FFF/FDM, SLA, SLS | Custom enclosures, brackets, grips, complex shapes |
| Subtractive | Remove material from a larger piece of stock | CNC routing, milling, laser cutting | Panels, plates, slots, precise flat parts |
| Forming / joining | Shape or connect material without building the whole part through a toolpath | Bending sheet, casting, fastening, gluing | Flexible surfaces, assemblies, repairable instruments |

The machine does not remove the need for design decisions. Each process has a different relation to geometry, material, scale, finish, tolerances, and assembly. A part that is easy to print may be awkward to machine from a sheet; a laser-cut panel may be more useful as one face of a multi-part instrument than as a complete enclosure.

### Discussion: choose the process after the object

Ask what the part needs to do before choosing a machine. A flat faceplate with labelled holes may be a good laser-cut part. A rounded ergonomic grip may be easier to print. A thick hardwood body with a smooth cavity might suit CNC routing. A hybrid instrument may combine all three with screws and off-the-shelf hardware.

---

## 3. 3D printing technologies (18–42 min)

### 3.1 Material extrusion: FFF / FDM

Material extrusion feeds thermoplastic filament through a heated nozzle. The nozzle deposits paths layer by layer until the object is built. **Fused filament fabrication (FFF)** is the generic process name; **fused deposition modeling (FDM)** is a widely used commercial term.

This is the most familiar desktop 3D-printing process for many students and makers. Common materials include PLA, PETG, ABS/ASA, and flexible TPU, each with different properties and print requirements.

**Useful for:** enclosures, brackets, buttons, knobs, clips, grips, mounting fixtures, and quick shape prototypes.

**Design consequences:**

- The part is built in layers, so strength can differ by direction. A thin arm may split more easily across its layers than along them.
- Overhangs may need support material or a changed orientation.
- Holes, slots, and thin walls need enough clearance and thickness for the printer and material.
- Orientation affects visible layer lines, surface finish, support marks, print time, and strength.
- Parts that must fit together often need a clearance test instead of assuming the CAD dimensions will fit exactly.

### 3.2 Vat photopolymerization: SLA, DLP, and MSLA

Vat photopolymerization hardens liquid resin with light. In **SLA**, a laser traces the layer; **DLP** projects a layer image; **MSLA/LCD** exposes a layer through a light source and masking screen. Implementations differ, but all cure photosensitive liquid into a solid part.

**Useful for:** fine details, small buttons or knobs, smooth surfaces, miniatures, and prototypes where surface quality matters.

**Design and process consequences:**

- Parts often need supports and careful orientation.
- Uncured resin must be removed; washing and post-curing are commonly part of the process.
- Resin is a chemical material. Follow the printer and workshop requirements for handling, ventilation, protective equipment, and waste.
- Material properties differ from familiar thermoplastics; select a resin for the intended use rather than judging by appearance alone.

### 3.3 Powder bed fusion: SLS and metal processes

Powder bed fusion uses thermal energy to fuse selected areas in a powder bed. **Selective laser sintering (SLS)** commonly produces polymer parts; metal powder-bed systems use a laser or electron beam to fuse metal powder.

**Useful for:** complex parts, interlocking structures, and geometries that would otherwise need many supports. SLS parts can be useful for durable enclosures, brackets, or small-batch components when equipment and service are available.

**Design and process consequences:**

- Unfused powder supports parts during the build, but it must be removed afterward.
- Surface texture and dimensional tolerances differ from FFF and resin processes.
- Equipment, material handling, and post-processing needs are more specialized than typical desktop printing.

### 3.4 Other additive processes

The ISO/ASTM additive-manufacturing vocabulary groups processes into seven broad families. In addition to material extrusion, vat photopolymerization, and powder bed fusion, these include:

- **Material jetting:** deposits droplets of build material, often with curing. It can produce detailed, multi-material parts on specialized systems.
- **Binder jetting:** deposits a binder to join regions of powder; the part may require further processing.
- **Directed energy deposition:** deposits material while a focused energy source melts it, often for metal repair or large industrial parts.
- **Sheet lamination:** bonds sheets of material to build a part.

These industrial processes are useful to know as a map of the field. The course’s practical emphasis is on selecting an appropriate process for a small instrument component, often FFF, resin printing, laser cutting, or CNC routing.

### 3.5 Choosing a printing process

| Question | Why it matters |
|---|---|
| Is the part a quick prototype or a finished component? | Prototype parts can prioritize iteration; a finished part needs suitable material and finish. |
| Does it need to flex, withstand impact, or carry a load? | Material and build orientation affect mechanical behavior. |
| Are small details or a smooth surface essential? | Resin processes can capture fine details but add handling and post-processing. |
| Is the geometry hard to support or assemble? | Build process and part orientation can change the design. |
| Can it be divided into simpler parts? | A two-part enclosure may be easier to print, service, and revise. |
| How will it connect to sensors, electronics, and a performer? | Mounting, access, cable routing, and comfort are functional requirements. |

The “best” process depends on the role of the part, the available machine and material, workshop constraints, and how many iterations the project can support.

---

## 4. CAD and design for fabrication (42–54 min)

### 4.1 CAD is a design space, not just a drawing tool

Computer-aided design (CAD) describes the geometry and relationships of a part. A parametric CAD model can preserve dimensions and constraints so that the design can be revised coherently. A mesh or sculpting tool may be better for organic forms. A 2D vector drawing is often the right starting point for flat profiles and laser-cut parts.

Examples of software include:

- **3D parametric CAD:** FreeCAD, Autodesk Fusion, Onshape, SolidWorks.
- **Mesh and organic modeling:** Blender, Meshmixer and similar tools.
- **2D vector drawing:** Inkscape, Illustrator, and machine-specific laser software.
- **Slicers:** PrusaSlicer, Cura, OrcaSlicer, Bambu Studio, PreForm for compatible systems.
- **CAM:** FreeCAD Path/CAM, Fusion Manufacture, and machine-specific CAM tools.
- **Machine preparation / control:** LightBurn for supported laser systems, printer host software, or the CNC controller interface.

These names are examples rather than endorsements. Some applications combine CAD, CAM, and machine preparation; others specialize in one step. Always confirm that the chosen software supports the actual machine and its file format.

### 4.2 Design for assembly and play

For a musical interface, a part must fit both its components and a human action. Before modeling, identify:

- component dimensions and mounting-hole locations;
- button, knob, sensor, connector, and display positions;
- cable bends, access to USB or power, and room for fasteners;
- wall thickness, clearances, moving parts, and how parts will be assembled;
- reach, grip, posture, tactile feedback, and the possibility of playing without watching the control;
- access for repair, sensor replacement, and firmware updates.

Use component datasheets and physical measurements. Add clearance for manufacturing variation and assembly. A quick test coupon or a small print of a connector opening can reveal fit problems before the full enclosure is made.

### Discussion: why not print the whole instrument as one part?

Separate components can be easier to print, repair, and revise. A modular object can use a printed grip, a laser-cut faceplate, standard screws, a replaceable sensor mount, and a microcontroller board. Splitting the design may also improve access and reduce wasted material.

---

## 5. Short break (54–64 min)

Prompt students to notice how objects around them are assembled. Which parts appear molded, printed, machined, cut from sheet, or fastened together? What design choices are visible at the joints?

---

## 6. From 3D CAD to slicer to printer (64–79 min)

### 6.1 The workflow

```text
CAD model → export / project file → slicer → previewed layers and toolpaths
     → printer-specific machine file → fabrication → support removal / finishing
     → assembly → test with performer → revise CAD
```

The CAD model describes the object. The slicer prepares that model for a specific printer and material. It turns the geometry into successive layers, perimeters, infill, supports, and movement instructions. Depending on the machine, the output may be G-code or a manufacturer-specific job file.

### 6.2 Typical file handoff

- **STL:** common mesh format for a single surface model. It does not preserve the original parametric design history.
- **3MF:** a 3D-printing project format that can carry model and print-plate information; useful when the slicer supports it.
- **STEP:** a solid-model exchange format often used when moving editable geometry between CAD and CAM tools.

The right export depends on the next application. Check units and scale after import. A model that appears tiny or enormous may have a unit mismatch.

### 6.3 What the slicer controls

- **Orientation:** affects strength, surface finish, supports, and time.
- **Layer height:** affects vertical detail and build time.
- **Perimeters and wall thickness:** influence durability and the quality of screw holes or enclosures.
- **Infill:** supports upper surfaces and can alter weight and stiffness; it does not replace adequate walls where the part needs strength.
- **Supports and adhesion aids:** help difficult geometry stay attached during the print; they also need removal.
- **Material profile:** temperature, cooling, speed, and other settings depend on the printer and material.

Students do not need to memorize settings at this stage. They should understand that slicing is a manufacturing decision. The same CAD model can produce different parts when orientation, material, walls, supports, or printer profile change.

### 6.4 Inspect before printing

Use the slicer’s preview to inspect the actual planned layers and paths. Look for unsupported regions, missing walls, unexpected gaps, poor bed contact, support structures inside inaccessible cavities, and a likely weak orientation. Confirm the part fits within the machine volume and that the selected printer and material profile are correct.

### 6.5 After printing

Remove supports and clean the part as appropriate for the process. Check the fit of controls, boards, and fasteners. Assemble the instrument, then test it with the intended gesture. Note what feels wrong: a sharp edge, a loose knob, a hidden connector, a sensor that moves, or a grip that forces an awkward posture. Return those observations to the CAD model for the next version.

---

## 7. CNC routing and CAM (79–94 min)

### 7.1 What a CNC router does

A CNC router uses a rotating cutting tool to remove material from a workpiece. It is particularly useful for sheet goods and larger parts in wood, plastics, and some other machine-compatible materials. Many router projects are 2D or **2.5D**: the tool cuts profiles, slots, pockets, and shallow shapes at different depths while the workpiece stays in one orientation.

**Musical-interface uses:** a wooden instrument body, a faceplate, a recessed control surface, a cavity for electronics, a large mounting plate, or a repeatable set of parts.

### 7.2 Design consequences

- A round tool cannot make a perfectly sharp internal corner. Internal corners need a radius or a dog-bone relief if a square component must fit.
- Narrow slots and small features are limited by tool diameter and reach.
- The workpiece must be held securely. Workholding affects what areas the cutter can reach.
- Cut depth, tool choice, stock thickness, and setup affect the result.
- Parts may need tabs or another holding strategy so that the final cut does not release them unexpectedly.

### 7.3 CAD-to-CAM workflow

```text
CAD solid → CAM setup (machine, stock, origin, tool) → toolpaths
     → simulation and review → postprocessor → machine-specific NC / G-code
     → router and workholding → deburr / finish → assemble and test
```

In CAM, the operator defines the stock, work coordinate system (WCS), tool, operations, and cutting strategy. The software generates and simulates toolpaths. A **postprocessor** translates those paths into code suited to the particular machine and controller. G-code is not automatically interchangeable between CNC machines.

Simulation helps identify unreachable features, collisions, and incorrect setups. It does not replace checking the real stock, tool, workholding, machine limits, and workshop procedure.

### 7.4 Software examples

FreeCAD Path/CAM and Autodesk Fusion Manufacture are examples of tools that connect solid models to CAM setup, toolpaths, simulation, and machine-specific post-processing. A simple router may instead use a more specialized 2D CAM package. Choose the postprocessor for the actual machine and verify the output through the approved workflow.

---

## 8. Laser cutting and other sheet processes (94–108 min)

### 8.1 Laser cutting

A laser cutter follows a path across sheet material. Vector paths can be used for cuts or line marking; filled areas or raster images can be used for engraving. The software assigns operations and settings to groups or layers. For example, a design might engrave labels, score fold lines, and cut the outer profile in a planned order.

**Musical-interface uses:** faceplates, labels, stencils, acrylic or plywood panels, finger guides, flat enclosures, and layered assemblies.

**Design considerations:**

- A laser cuts 2D profiles from sheet stock; a three-dimensional object usually needs tabs, slots, spacers, bending, or fasteners.
- The kerf removes material along the cut. Tight-fitting parts need the kerf and material thickness accounted for.
- Lines that overlap can be cut more than once; inspect duplicates and closed paths.
- Engraving and cutting are different operations and are commonly ordered so that internal details are marked before the part is released from the sheet.
- Material compatibility, extraction, fire prevention, and supervision are machine- and workshop-specific. Confirm that the material is approved for the machine and follow local safety rules; do not infer safety from a material’s appearance.

### 8.2 Typical laser workflow

```text
2D vector drawing → vector cleanup and scale check → operation layers
     → machine/material settings → preview and test piece → cut / engrave
     → assemble layers → fit electronics and test the interface
```

LightBurn is one example of software that organizes vector and image work into operation layers for compatible laser systems. Inkscape and other vector editors can create the underlying 2D geometry. Some machines instead use their own software and file conventions.

### 8.3 Other useful digital fabrication processes

- **Vinyl cutting:** cuts thin adhesive vinyl or similar sheet materials. Useful for labels, masks, overlays, and decorative or tactile markings, rather than structural parts.
- **Waterjet cutting:** uses a high-pressure water stream, often with abrasive, to cut sheet or plate materials on specialized equipment.
- **Digital embroidery:** converts vector-like patterns into stitch instructions; useful for conductive textiles and wearable interfaces.
- **PCB milling and fabrication:** produces circuit-board prototypes through specialized processes, but the design and electrical rules require a separate lesson.
- **Hand tools and conventional workshop processes:** sanding, drilling, bending, fastening, and finishing often complete a digitally fabricated object.

### 8.4 Hybrid construction

Different processes can complement one another. A small DMI might use a 3D-printed grip and sensor mount, a laser-cut faceplate, an off-the-shelf microcontroller, and standard screws. The choice should follow function: a fastener should remain accessible, a sensor should stay in place, and the assembled object should support the intended movement.

---

## 9. Design exercise: fabricate a musical controller (108–116 min)

### Brief

Design a handheld sound controller with:

- one continuous control (for example, a knob, pressure surface, or bending gesture);
- one discrete control (for example, a button or switch);
- an accessible connection to a microcontroller and a cable or battery;
- a clear way for the performer to understand and repeat the gesture.

### Group task

In five minutes, sketch the object and its fabrication plan. In three minutes, each group gives a short report. Include:

1. The performer’s action and how the object is held or placed.
2. The component layout: sensor, button, microcontroller, connector, and cable path.
3. The proposed process for each major part: print, laser cut, CNC route, or buy/assemble.
4. The software path and file handoff: CAD, vector drawing, slicer, CAM, and/or machine-control software.
5. One likely fit, strength, comfort, or repair issue, and a way to test it.

Encourage a hybrid plan. Students do not need to model the object in software; the objective is to connect the physical interaction to a plausible fabrication sequence.

### Debrief questions

- Which part sets the performer’s posture or grip?
- Which dimensions should be measured before modeling?
- What needs to remain accessible for assembly or repair?
- What is the first cheap prototype that could test the most important uncertainty?
- Which process choice depends on workshop access or safety training?

---

## 10. Summary and exit question (116–120 min)

### Key ideas

1. Additive, subtractive, and sheet-based processes shape material in different ways.
2. 3D printing is a family of technologies, not a single process.
3. CAD describes the object; slicers and CAM tools prepare it for a specific machine and process.
4. Machine files depend on the machine, material, process, and setup. A file that works for one machine may not suit another.
5. Fabrication choices affect how an instrument is assembled, held, played, repaired, and perceived.
6. A quick prototype should answer a question. It can test fit, reach, strength, balance, or gesture before the full object is made.

### Exit question

> Choose one part of a musical instrument you would fabricate. Which process would you use, what software would prepare the job, and what would you test first?

---

## Software and references

Software names below are examples. Current machine compatibility, licensing, formats, and interfaces should be checked before a project begins.

- [ISO/ASTM 52900: Additive manufacturing vocabulary](https://www.iso.org/standard/74514.html)
- [NIST: Additive Manufacturing Technologies](https://www.nist.gov/additive-manufacturing/research-areas/technologies)
- [Prusa Knowledge Base: First print with PrusaSlicer](https://help.prusa3d.com/article/first-print-with-prusaslicer-2-9_1753)
- [Autodesk Fusion: Manufacture overview](https://help.autodesk.com/view/fusion360/ENU/?guid=GUID-BEC5DEA9-AC3E-4FA8-998E-4AE8CD0D0B1E)
- [Autodesk Fusion: Setups for manufacturing](https://help.autodesk.com/view/fusion360/ENU/?contextId=MFG-SETUP-2ND-SIDE)
- [LightBurn: Colors and layers](https://docs.lightburnsoftware.com/2.0/GetStarted/ColorsAndLayers/)
- [Harvard Environmental Health & Safety: Laser cutter pre-use checklist](https://www.ehs.harvard.edu/sites/default/files/laser_cutter_preuse_checklist.pdf)

### Instructor note on machine safety

This lecture explains process concepts and file workflows; it is not machine-operation training. Laser cutters, CNC routers, resin printers, and other fabrication equipment have different hazards and operating requirements. Students should use machines only after the relevant local training, with approved materials and machine-specific procedures. For laser work, material approval, functioning extraction, supervision, and fire precautions are essential workshop controls. For machining, follow the shop’s rules for enclosure, workholding, dust or fume control, tools, and emergency stops.
