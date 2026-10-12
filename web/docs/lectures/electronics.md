# Basic Electronics and Analog Sensors

## The Teensy 4.0

* Technical information and the connection layout for the Teensy 4.0 can be found on PJRC’s website: [https://www.pjrc.com/store/teensy40.html](https://www.pjrc.com/store/teensy40.html)

## Introduction to Electronics

* The following page:
  [https://ccrma.stanford.edu/wiki/Introduction_to_Electronics_(condensed)](https://ccrma.stanford.edu/wiki/Introduction_to_Electronics_%28condensed%29)
  provides a good overview of basic electronics concepts for building interfaces. It is highly recommended reading :).

## Using a Potentiometer or a Button with the Teensy

* The following circuit:

<img src="../../res/diagram.jpg" width="70%" class="mx-auto d-block">

allows you to connect a potentiometer and a button to a Teensy.

* Here's the corresponding picture:

<img src="../../res/board0.jpg" width="70%" class="mx-auto d-block">

<img src="../../res/board1.jpg" width="70%" class="mx-auto d-block">

* The values from these different elements can be displayed in the serial debugger as follows:

```
void setup(){
  pinMode(0,INPUT);
  Serial.begin(9600);
}

void loop(){
  int potVal = analogRead(A0);
  if(digitalRead(0)){
    Serial.println("On :)");
  }
  else{
    Serial.println("Off :(");
  }
  Serial.print("Pot Val: ");
  Serial.println(potVal);
  delay(100);
}
```

## Exercise 

## Mapping Printed Values

* Modify the range of the potentiometer so that printed values are between 300 and 400 instead of 0 and 1023.
* When pressing the button, values should be between 400 and 500.

### Possible Solution

```
void setup(){
  pinMode(0,INPUT);
  Serial.begin(9600);
}

void loop(){
  int offset = 0;
  if(digitalRead(0)){
    offset = 100;
  }
  int potVal = analogRead(A0)/1023*100 + 300 + offset;
  Serial.print("Pot Val: ");
  Serial.println(potVal);
  delay(100);
}
```

## Implementing a Switch

* Modify the code from the [first assignment](../assignments/random.md) so that switching to a new note happens when pressing the button instead of every *n* milliseconds. New notes should be selected once at a time: pressing the button once triggers only one new note. 

### Possible Solution

```
int state = HIGH;      // the current state of the output pin
int reading;           // the current reading from the input pin
int previous = LOW;    // the previous reading from the input pin

// the follow variables are long's because the time, measured in miliseconds,
// will quickly become a bigger number than can be stored in an int.
unsigned long t = 0;           // the last time the output pin was toggled
unsigned long debounce = 200UL;   // the debounce time, increase if the output flickers

char *notes[] = {"Do","Re","Mi","Fa","Sol","La","Si"};

void setup()
{
  pinMode(0,INPUT);
  Serial.begin(9600);
}

void loop()
{
  reading = digitalRead(0);

  // if the input just went from LOW and HIGH and we've waited long enough
  // to ignore any noise on the circuit, toggle the output pin and remember
  // the time
  if (reading == HIGH && previous == LOW && millis() - t > debounce)
  {
    if (state == HIGH)
      state = LOW;
    else{
      state = HIGH;
      Serial.println(notes[random(7)]);
    }

    t = millis();
  }

  previous = reading;
}
```
