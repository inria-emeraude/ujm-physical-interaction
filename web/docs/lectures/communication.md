# Serial and MIDI Communication

## Serial Control of a Processing Program with a Teensy

* In this section, we show how to control a Processing program ([https://processing.org/](https://processing.org/)) with a Teensy.

### What's Serial?

Serial is a way of transmitting digital data "bits by bits." In that regard, it is one of the most basic digital communication protocol. The Arduino serial protocol uses 8 bits words.

### Arduino Program

```
int val = 0;
void setup(){
  Serial.begin(9600);
}

void loop(){
  Serial.println(val);
  val = (val + 1)%255;
  delay(10);
}
```

### Processing Program

```
import processing.serial.*;

Serial myPort;
static String val;
int sensorVal = 0;

void setup()
{
  fullScreen(P3D);
  noStroke();
  fill(204);
  String portName = "/dev/ttyACM0";
  myPort = new Serial(this, portName, 9600);
}

void draw()
{
  if ( myPort.available() > 0) {
    val = myPort.readStringUntil('\n');
    try {
      sensorVal = Integer.valueOf(val.trim());
    }
    catch(Exception e) {
      ;
    }
  }

  background(0);
  float recWidth = width/4*sensorVal/255;
  fill(255,0,0);
  square(width/2-recWidth/2, height/2-recWidth/2, recWidth);
}

```

## MIDI Control With the Teensy

This example shows how to use a Teensy to control a Faust program using USB MIDI.

### What's MIDI?

MIDI is an 8 bits communication protocol used in the context of music. It dates back from 1983 and it is still in use nowadays! MIDI was designed to transmit note numbers, velocity but also generic information through control changes.

More information on MIDI can be found on Wikipedia: <https://en.wikipedia.org/wiki/MIDI>

### Teensy Program

Choose `Tools/USB Type/MIDI`.

```
void setup() {
}

void loop() {
  usbMIDI.sendControlChange(0,random(0,127),0);
  delay(100);
}
```

### Faust Program

Choose the Teensy as a MIDI input in the Faust IDE.

```
import("stdfaust.lib");
f = hslider("freq[midi: ctrl 0]",440,50,2000,0.01) : si.smoo;
process = os.sawtooth(f)*0.9;
```
