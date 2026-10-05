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

## Implementing a Switch

* Modify the code from the [first assignment](../assignments/random.md) so that switching to a new note happens when pressing the button instead of every *n* milliseconds. New notes should be selected once at a time: pressing the button once triggers only one new note. 
