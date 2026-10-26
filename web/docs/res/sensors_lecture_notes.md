# Sensors and Sensor Technologies for Musical Interaction

## 1. Opening: what counts as sensing? (0–8 min)

### Opening question

> When does a movement become a musical control?

Invite students to name examples: pressing a key, bowing a string, tilting a phone, turning a knob, moving a hand in front of a camera, blowing into a microphone, or touching a conductive surface.

Ask whether all of these are “sensors.” The useful first distinction is that some actions are sensed by a dedicated component, while others are detected through a conventional musical interface or by analyzing an existing signal. A keyboard key may use a switch; a camera tracks visual change; a microphone converts pressure variation in air into an electrical signal. All provide information about a physical event, but they do so through different principles and with different relationships to the player.

### Working definition

A **sensor** is a device or system that responds to a physical phenomenon and produces a signal that another system can use.

The phenomenon might be pressure, motion, light, sound, temperature, magnetic field, distance, or a property of the body. A sensor’s output is not the gesture itself. It is a measurable trace from which a system may infer something useful.

### Quick classification prompt

For each example, ask: what physical phenomenon changes, and what does the system observe?

| Example | Physical phenomenon | Possible observation |
|---|---|---|
| Potentiometer knob | Rotation | Changing electrical resistance or voltage |
| Push button | Contact / force | Open or closed circuit |
| Accelerometer | Linear acceleration | Acceleration along one or more axes |
| Camera | Light arriving at an image sensor | A changing image or tracked features |
| Microphone | Air pressure variation | An electrical audio signal |

Emphasize that “sensor” can refer to a component, a module, or a larger sensing system. A camera plus computer-vision software, for example, is a sensing system even though the camera alone does not identify a hand gesture.

---

## 2. From physical event to musical consequence (8–18 min)

Introduce the chain below. It helps students avoid treating a sensor reading as if it already had musical meaning.

```text
physical event → transduction → signal → interpretation → musical consequence
     press       force sensor    value     “how hard?”     louder / brighter
```

### Key terms

- **Physical event:** Something happens in the world: a surface is pressed, a body turns, a string vibrates.
- **Transduction:** A sensor converts one kind of physical change into another form, commonly an electrical signal.
- **Signal:** The changing value made available to the system. It may be continuous, discrete, or a stream of images or samples.
- **Interpretation:** The system decides what the signal means in context. Is a hand approaching? Is a pressure change intentional? Has a gesture started or ended?
- **Musical consequence:** The sound or behavior affected by the interpreted signal: triggering a note, changing timbre, moving a sound in space, or selecting a mode.

### The sensor is not the gesture

The same sensor reading can have different meanings in different instruments. A rising accelerometer value may mean “increase brightness,” “move the sound upward,” “select the next sound,” or nothing at all. A camera may detect a hand, but it cannot determine whether the hand is performing, resting, or accidentally crossing the frame without additional design choices.

Likewise, the same gesture can be sensed in different ways. A performer’s bending motion might be captured with a flex sensor, a camera, an inertial sensor attached to the body, or a distance sensor observing the limb. Each option affords a different playing posture and produces different data.

### Discussion: intention and ambiguity

Ask students:

1. If a performer shakes a controller, how could the system distinguish an intentional gesture from an accidental bump?
2. If a hand is visible to a camera, what else would the system need to know before deciding what the hand is doing?
3. Is ambiguity always a problem, or can it be musically useful?

The goal is not to eliminate ambiguity at all costs. Ambiguous or unstable behavior can be part of an instrument’s character, but it should be a deliberate design choice. The performer needs to be able to learn the relationship and decide how to use it.

---

## 3. Sensor families I: contact, force, and deformation (18–43 min)

These sensors detect events at or near a physical interface. They are often easy to understand because the performer can see and feel the contact that produces the signal.

### 3.1 Switches and buttons

A switch reports a small number of states, often open/closed or on/off. A button can trigger a note, change a mode, select a sound bank, or confirm an action.

**Musical qualities:** clear onset, strong causal relationship, easy to learn, useful for discrete events.

**Questions and limitations:** Is the button easy to reach while playing? Does it require too much force? Can it be triggered accidentally? Does its binary behavior fit the musical idea, or is continuous control needed?

Switches include familiar keys and buttons, but also magnetic reed switches, microswitches, and contacts made from conductive materials. A switch is a sensor even when it is built into a larger control such as a keyboard key.

### 3.2 Potentiometers and rotary controls

A rotary potentiometer converts the rotation of a shaft into a changing electrical value. A slider potentiometer does the same for linear motion. They are common in knobs, faders, and simple controllers.

**Musical qualities:** continuous value, visible position, direct manual control; especially useful for parameters such as level, cutoff, or blend.

**Questions and limitations:** Does the control have a useful physical range? Can the performer find it without looking? Is a knob appropriate for a parameter that changes quickly? What happens when the control reaches its limit?

Other rotary technologies include encoders, which report movement in steps and can often turn indefinitely. Unlike a potentiometer, an encoder may not have a physical position that corresponds to the parameter’s current value. That can be useful for selecting values or navigating menus, but it changes how the control communicates state.

### 3.3 Force, pressure, and touch

Pressure-sensitive components respond to force or pressure. Examples include force-sensitive resistors, pressure pads, load cells, capacitive touch surfaces, and pressure sensors in air or fluid systems.

**Musical qualities:** continuous or graded control; can link touch intensity to dynamics, brightness, articulation, or density; can support playing across a surface rather than pressing a conventional button.

**Questions and limitations:** Is pressure measured consistently across the surface? Does the player need tactile feedback? Can the sensor distinguish a light touch from a firm press? How will the interaction work with gloves, sweat, or different hand sizes?

Touch is not the same as force. A capacitive surface can detect a finger’s presence without measuring how hard it presses. A pressure sensor may measure force but may not know where on a broad surface the force occurred. Choosing between them depends on the intended musical action.

### 3.4 Bend, stretch, and deformation

Flex sensors, stretch sensors, bend-sensitive materials, and conductive textiles change their electrical properties as they deform. They can be attached to gloves, fabric, soft objects, or flexible structures.

**Musical qualities:** can make the body or a soft object part of the interface; can follow continuous deformation; can support unusual postures and tactile forms.

**Questions and limitations:** Is the sensor measuring the intended movement, or also nearby movement? Does it return to the same value after repeated bending? Is it comfortable and robust when worn? How should the performer calibrate it?

### 3.5 Piezoelectric and vibration sensing

Piezoelectric materials produce an electrical response when they are bent, struck, or vibrated. They are often used as contact microphones, impact sensors, or pickups attached to surfaces.

**Musical qualities:** can detect taps, impacts, vibration, and onset details; can turn an object’s material resonance into part of the instrument; small and easy to attach.

**Questions and limitations:** A piezo element is sensitive to how and where it is mounted. It may respond strongly to impacts and vibrations, but it is not automatically a precise measure of sustained force. It can pick up unwanted knocks or stage vibration.

### Compare: one musical intention, several sensors

Suppose a performer wants to control the brightness of a sound while bending a finger.

- A **flex sensor** attached to the finger measures bending, but it affects comfort and may need calibration.
- A **camera** can observe the finger without attaching a sensor, but needs a clear view and may be affected by lighting or occlusion.
- An **inertial sensor** on the hand measures motion, but may not isolate one finger’s bend.
- A **pressure surface** could capture a related expressive action, such as squeezing, but changes the gesture itself.

There is no universally best sensor. The choice changes the performer’s action, not just the data format.

---

## 4. Short break and observation prompt (43–53 min)

Ask students to look around the room or at objects they have with them. Identify one object that senses something and one that actuates or changes something. What would change if the same object were used as a musical interface?

Examples might include a phone touchscreen, a laptop trackpad, a game controller, a door handle, a smartwatch, or a wireless earbud.

---

## 5. Sensor families II: motion, distance, light, sound, and body signals (53–75 min)

### 5.1 Inertial sensors: accelerometers and gyroscopes

An **accelerometer** measures acceleration. In practice, this can provide information about tilt relative to gravity, movement, vibration, or impacts. A **gyroscope** measures rotational speed. Devices often combine several axes of these sensors in a small inertial measurement unit (IMU); some also include a magnetometer, which senses magnetic field direction.

**Musical qualities:** compact, wearable, and usable without a camera; can follow handheld objects or body parts; useful for tilt, shake, rotation, and movement intensity.

**Questions and limitations:** The sensor measures motion, not a musical gesture category. Stillness, drift, orientation, and attachment position matter. A sensor on the wrist cannot necessarily distinguish wrist rotation from movement of the whole arm.

Ask: what does an “up” direction mean if the instrument rotates? How could a performer reset or calibrate their position? Would a noisy but responsive signal be better for a particular sound than a very stable one?

### 5.2 Position, proximity, and distance

Distance and proximity sensors detect whether something is nearby or how far away it is. Technologies include infrared, ultrasonic, optical time-of-flight, and radar sensing. They differ in range, field of view, accuracy, response, and sensitivity to environmental conditions.

**Musical qualities:** support contact-free interaction; can make movement through space part of an instrument; useful for approach, withdrawal, and spatial control.

**Questions and limitations:** What objects are detected? How broad is the sensing region? Can two hands be distinguished? Does the system behave differently under sunlight, in a reflective room, or with multiple performers nearby?

### 5.3 Cameras and computer vision

A camera measures patterns of light over an image. Software can track image features, color regions, markers, body joints, hands, or objects. Depth cameras add distance information for pixels or regions in the image.

**Musical qualities:** capture detailed movement without requiring a wearable sensor; can observe several performers or large gestures; supports visual feedback and audience-visible interaction.

**Questions and limitations:** The camera needs a view of the performer. Lighting, background, clothing, occlusion, and camera position affect what can be detected. A system may track a body part without knowing its intention. The performer may need to adapt to a designated stage area or keep certain movements visible.

Consider the difference between “the system sees the hand” and “the system understands the gesture.” The latter depends on tracking, interpretation, training examples, and the conditions in which the system is used.

### 5.4 Microphones and acoustic sensing

A microphone converts changes in air pressure into an electrical signal. It may be used to capture voice or an instrument, but also to detect claps, taps, breath, environmental events, or the acoustic response of an object.

**Musical qualities:** sound itself can become the control signal; supports voice, breath, and acoustic gestures; can avoid adding a visible control surface.

**Questions and limitations:** The microphone may hear the loudspeakers as well as the performer. Room acoustics, noise, distance, and feedback can influence the signal. A microphone does not automatically separate one intended sound from everything else.

### 5.5 Biosignals and physiological measures

Some systems measure signals from the body, such as muscle activity (EMG), heart activity (ECG), or brain activity (EEG). These approaches can be compelling, but their outputs are often subtle, variable, and highly dependent on contact, placement, movement, and interpretation.

**Musical qualities:** can explore exertion, tension, breath, or physiological change as part of performance; may support interactions where conventional movement is limited.

**Questions and limitations:** Is the signal reliable enough for the intended performance? Is the setup comfortable and repeatable? Does the system make a defensible claim about what is being measured? A biosignal should not be treated as a transparent readout of emotion or intention.

### 5.6 Environmental sensors

Light, temperature, humidity, air quality, and other environmental measures can influence a musical system. They may respond slowly, which can be appropriate for installations or evolving compositions but less useful for fast control gestures.

Ask whether the audience or performer should be able to perceive the connection between the environment and the sound. A change in room temperature that slowly alters a soundscape may make sense in an installation; it may be a poor choice for triggering a precisely timed note.

---

## 6. From sensor to microcontroller (75–93 min)

The sensing principle describes what physical quantity changes. The sensor’s **electrical interface** describes how that change becomes available to a microcontroller. Two sensors measuring the same thing, such as distance, may use different interfaces: one may provide an analog voltage, while another may contain its own conversion electronics and communicate digitally over I²C or SPI.

```text
physical quantity → sensing element / module → electrical signal or data protocol
       pressure              sensor                    voltage / GPIO / I²C / SPI
                                                        ↓
                                                microcontroller input
```

This is a useful bridge between choosing a sensor and programming an instrument. The connection affects what hardware is needed, how many pins are used, how quickly values can be read, and how much circuitry or software is involved. The protocol does not determine the musical meaning of the signal; interpretation and mapping come afterward.

### 6.1 Analog outputs and ADC inputs

An analog sensor produces a continuously varying electrical quantity, commonly a voltage. A microcontroller’s analog-to-digital converter (ADC) samples that voltage and represents it as a number. A potentiometer used as a voltage divider is a familiar example: turning the shaft changes the voltage at its output, and the ADC converts that voltage into a digital value.

Some sensors do not directly output a voltage. A thermistor or a force-sensitive resistor, for example, changes its resistance. It needs a suitable circuit, often a voltage divider, before its state can be read by an ADC. Other analog sensors need amplification or filtering. The sensor’s datasheet and the microcontroller’s input range determine how to connect it safely.

**Useful properties:** simple, direct, and common for continuous controls such as potentiometers, light-dependent resistors, and many force or flex sensors.

**Things to check:**

- The microcontroller’s maximum input voltage. A 5 V signal can damage a 3.3 V-only input.
- ADC resolution and input range. These affect how finely a voltage is represented, but do not guarantee that the sensor itself is precise or stable.
- Whether the signal needs conditioning, such as a divider, amplifier, or filter.
- How many ADC channels are available and whether the required pins are already used by other hardware.

### 6.2 Digital GPIO: switches and logic signals

A digital input reads one of a small number of logic states, usually interpreted as LOW or HIGH. A push button or limit switch can be read this way. Many microcontrollers also provide internal pull-up or pull-down resistors so an unpressed switch has a stable default state rather than a floating input.

Digital does not always mean “a sensor with a data protocol.” A simple switch can connect directly to a GPIO pin, while a digital sensor module may send structured data over I²C or SPI. A switch can also produce rapid transitions as its contacts settle, called **contact bounce**; software or hardware debouncing prevents one press from being interpreted as several.

Some sensors communicate through pulse timing or frequency rather than a voltage level or a multi-wire bus. An ultrasonic distance module, for example, may signal a measurement using the duration of a pulse. In that case, the microcontroller measures timing on a GPIO pin.

### 6.3 I²C: a shared two-wire bus

I²C (Inter-Integrated Circuit) is a serial communication bus commonly used for small sensors and control chips. It uses two signal wires: **SDA** for data and **SCL** for the clock, in addition to power and ground. A controller can communicate with several devices on the same bus, typically selecting each device by its address.

**Useful properties:** only two signal wires are needed; multiple addressed devices can share the bus; many small sensor breakout boards support it.

**Things to check:** devices need compatible logic voltage and addresses; some boards have fixed or configurable addresses; cable length and bus speed are limited by electrical properties of the bus. I²C is common for sensors such as accelerometers, gyroscopes, magnetometers, environmental sensors, and small displays.

### 6.4 SPI: a clocked, higher-throughput connection

SPI (Serial Peripheral Interface) is another common serial interface. A typical connection uses **SCLK** (clock), **MOSI** (controller-to-device data), **MISO** (device-to-controller data), and a **chip-select** line for each device. It often supports faster data transfer than I²C, and can be useful for sensors that produce larger or faster streams of data.

**Useful properties:** high throughput, straightforward full-duplex transfers in common configurations, and no device-address negotiation on the bus.

**Things to check:** it uses more signal wires, usually needs a separate chip-select line per device, and the sensor and microcontroller must agree on clock mode and maximum speed. SPI is common for fast motion sensors, displays, and memory devices.

### 6.5 UART and other connections

UART is an asynchronous serial connection using a transmit line (TX) and receive line (RX), plus a shared ground. It is common for GPS modules, some sensor boards, and communication between a microcontroller and another device. Unlike I²C and SPI, a basic UART connection does not share a clock wire; both ends must be configured for the same data rate and format.

Other interfaces include one-wire buses, CAN, and USB. These may be useful in particular systems, but the central design question remains the same: what signal does the sensor provide, and what does the microcontroller need in order to read it reliably? USB is more often used to connect a microcontroller or sensor interface to a computer than to connect a bare sensing element directly to a microcontroller pin.

### Interface comparison

| Sensor output / interface | Typical example | Connection idea | Main advantage | Main consideration |
|---|---|---|---|---|
| Analog voltage | Potentiometer, some light or force sensors | Signal to ADC input | Direct continuous value | Voltage range, ADC channels, and possible signal conditioning |
| Resistance change | Thermistor, force-sensitive resistor | Divider or conditioning circuit, then ADC | Simple sensing element | The element alone may not provide a readable voltage |
| Digital GPIO | Button, switch | Logic input pin | Simple discrete state | Pull-up/down and contact bounce |
| Pulse timing / frequency | Ultrasonic range module, pulse sensor | GPIO plus timer/capture | Encodes timing or rate | The program must measure pulse width or frequency |
| I²C | Many compact motion/environment sensors | SDA + SCL bus | Two signal wires; multiple addressed devices | Address conflicts, bus speed, wiring and voltage compatibility |
| SPI | Faster motion sensors, displays | Clock + data lines + chip select | High data throughput | More wires and device-specific configuration |
| UART | GPS or serial sensor module | TX + RX | Simple point-to-point serial data | Both ends must use matching settings |

### Keep the layers distinct

For any example, ask students to identify three separate things:

1. **What physical quantity is sensed?** For example, acceleration, pressure, light, or temperature.
2. **How does the sensor communicate it?** Analog voltage, switch state, pulse timing, I²C, SPI, or UART.
3. **What does the musical instrument do with the reading?** Trigger a sound, alter a parameter, classify a gesture, or control a spatial trajectory.

These layers can vary independently. An accelerometer is a sensing technology; I²C or SPI is a way of transferring its readings. A potentiometer is a rotary control; an ADC is how a microcontroller turns its voltage into a number. A digital reading is not automatically more accurate, and a higher-resolution ADC does not by itself make a more playable instrument.

### Practical safety and documentation note

Before connecting a sensor, check its supply voltage, output voltage, pin labels, and interface in the datasheet or module documentation. Sensor boards that look similar may require different voltages or wiring. In the course’s Teensy examples, the board’s input-voltage limits and pins already used by the audio shield matter. The electronics lecture develops the actual circuits and connection procedures.

---

## 7. Choosing a sensor: design tradeoffs (93–105 min)

Present sensor selection as a design question about the interaction, rather than a shopping question about component specifications.

### Questions to ask before choosing

1. **What physical action should matter?** Touch, pressure, rotation, vibration, movement through space, breath, or a change in the environment?
2. **What should the performer feel?** Contact, resistance, weight, texture, freedom of movement, or no physical object at all?
3. **What kind of control is needed?** A discrete trigger, a continuous value, a position, a direction, a gesture category, or a combination?
4. **Where is the interaction taking place?** At a desk, on a stage, in a gallery, in a crowded room, or while moving around?
5. **What should the audience be able to understand?** Is the causal link visible, or is hidden sensing part of the intended experience?
6. **What can go wrong in use?** Occlusion, drift, accidental touches, background noise, fragile attachments, inconsistent calibration, or restricted movement?
7. **How will the performer learn and control it?** Is feedback provided? Can the performer predict the result and recover from errors?

### A practical comparison table

| Sensor family | What it can observe | Typical interaction | Common design concern |
|---|---|---|---|
| Switch / button | Contact state | Trigger or selection | Accidental activation; limited states |
| Potentiometer / encoder | Rotation or position | Knob, slider, navigation | Physical range and visible state |
| Force / pressure / touch | Contact, force, or finger presence | Pressing, squeezing, touching | Force is not the same as touch; feedback and consistency |
| Flex / stretch | Deformation | Bending a wearable or soft object | Comfort, durability, calibration |
| Piezo / vibration | Impact or vibration | Striking, scraping, listening to an object | Mounting, unwanted vibration, poor sustained-force measurement |
| Accelerometer / gyroscope | Linear and rotational motion | Tilt, shake, rotation, movement | Orientation, attachment, drift, ambiguity |
| Proximity / distance | Nearby object or distance | Hovering, approach, spatial movement | Field of view, range, environment, multiple objects |
| Camera / depth camera | Image features, body parts, distance | Full-body or hand movement | Visibility, lighting, occlusion, interpretation |
| Microphone | Sound pressure | Voice, breath, taps, acoustic events | Background sound and feedback |
| Biosignal sensor | Electrical or physiological activity | Muscle or body-related control | Contact quality, variability, interpretation claims |

### Four recurring tradeoffs

- **Contact versus freedom:** A wearable or attached sensor can be close to the body, but may restrict movement or change the performer’s technique. Contact-free sensing allows freedom but may constrain the performer to a sensing area.
- **Precision versus expressiveness:** A highly stable control can be useful for accurate parameter setting. A more variable signal can create rich, responsive behavior when the performer can shape it musically.
- **Visibility versus hidden sensing:** A visible knob or gesture can help the audience understand cause and effect. Hidden sensing can create surprise, but may make the performance harder to read.
- **Rich data versus playable control:** More measured dimensions do not automatically make a better instrument. A small number of well-designed controls can be more expressive and learnable than many poorly connected measurements.

### Short analysis: “More data ≠ better instrument”

Invite students to imagine two controllers:

- Controller A senses one pressure value with an obvious and repeatable connection to the sound.
- Controller B uses a camera to extract many body landmarks, but the relationship between movement and sound is difficult to predict.

Which is more expressive? There is no universal answer. Ask what kind of music, performer, rehearsal process, and audience experience each design supports. Expression depends on the instrument’s possible actions, feedback, and learnability, not simply on the number of sensor channels.

---

## 8. Group design activity: choose the sensing approach (105–117 min)

Divide the class into small groups. Give each group one design brief, or let them select one.

### Design briefs

1. **A wearable sound controller:** A performer wants to change timbre through a slow, continuous hand gesture while keeping both feet free.
2. **An object instrument:** A wooden object should produce different sounds when tapped, rubbed, squeezed, or tilted.
3. **A spatial performance:** A performer wants to move a sound source around an audience without touching a controller.
4. **A breath instrument:** A performer wants to shape a sustained sound with breathing while also triggering discrete events.

### Group task

For each brief, students have 8 minutes to sketch a sensing design and 4 minutes for quick reports. Their sketch should include:

- the physical action to be sensed;
- one primary sensor family and one alternative;
- what the sensor actually measures;
- how its output could reach a microcontroller (for example, an ADC input, digital pin, I²C, or SPI);
- the musical parameter or event that could be controlled;
- one likely failure or ambiguity;
- a way to make the interaction learnable and playable.

Encourage students to draw the performer and sensor placement, not just a block diagram. Ask them to show what the performer does, what the system detects, and what sound changes.

### Debrief prompts

- Did the chosen sensor preserve or change the performer’s gesture?
- What could be confused with an intentional action?
- What information did the group decide not to measure?
- How would the performer know that the system detected the action?
- Would the design work on stage, or only in a controlled classroom?

---

## 9. Closing: the central ideas (117–120 min)

Return to the opening question: when does a movement become a musical control?

Summarize:

1. A sensor converts a physical phenomenon into a signal; it does not directly reveal intention.
2. Sensor technologies differ in what they can observe and in the actions they ask of the performer.
3. The same gesture can be sensed in many ways, and each way changes the instrument’s feel and constraints.
4. A good sensor choice begins with the desired interaction and musical behavior.
5. Sensor selection includes both the physical sensing principle and the electrical interface to the microcontroller.
6. A playable instrument needs a learnable relationship between action, feedback, and sound; more data alone does not provide that relationship.

### Exit question

> Name one gesture you would like to use in a musical instrument. What physical phenomenon could be sensed, and what would your first sensor choice make easy or difficult?

---

## Optional examples and teaching materials

Use these as demonstrations, short viewing/listening examples, or follow-up reading. They are optional; the lecture can be delivered without access to additional hardware.

- [Course overview: Physical Interaction Design @ UJM](https://inria-emeraude.github.io/ujm-physical-interaction/)
- [NIME: New Interfaces for Musical Expression](https://inria-emeraude.github.io/ujm-physical-interaction/lectures/nime/), including the course’s slides on [Technologies for Capturing Musical Gestures](https://inria-emeraude.github.io/ujm-physical-interaction/res/gesture_capture_lecture.pdf)
- [Basic Electronics and Analog Sensors](https://inria-emeraude.github.io/ujm-physical-interaction/lectures/electronics/): potentiometer and button examples, intended for the later practical electronics session
- [Mapping, Filtering, and Buying Stuff](https://inria-emeraude.github.io/ujm-physical-interaction/lectures/mapping/): follow-up on sensor ranges and filtering
- [NIME conference](https://www.nime.org/): examples of new interfaces and musical instruments
- [Gramophone project](https://gramophone.inria.fr/): an example of a musical installation using motion sensors, buttons, and potentiometers to control sound

### Simple in-room demonstrations

If objects are available, show a potentiometer, button, phone, microphone, and one motion or touch sensor. For each, have students identify the sensed phenomenon before naming the component. A phone can illustrate how several sensor families may coexist in one object (touchscreen, accelerometer, gyroscope, camera, microphone), while still requiring software to interpret their outputs.

### Instructor note: boundaries with other lectures

This class introduces sensing principles, common microcontroller interfaces, and interaction design. The existing electronics lecture can develop how to connect a potentiometer or button to a Teensy, while the mapping lecture can address range adjustment and smoothing. Camera-based capture, gesture recognition, and AI can be introduced here as broader sensing systems, then treated in more depth in their relevant sessions or project work.
