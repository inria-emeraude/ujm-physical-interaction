# Arduino Programming Basics

The microcontroller used in this course is the [Teensy 4.0](https://www.pjrc.com/store/teensy40.html). It can be programmed using the [Teensyduino Environment](https://www.pjrc.com/teensy/teensyduino.html). Install information can be found here: <https://www.pjrc.com/teensy/td_download.html>. The Teensy 4.0 is not an Arduino per se but works exactly the same way.

## Hello World

* The following program displays "Hello World" in the Serial Monitor every 0.5 seconds.
* The Serial Monitor can be opened by clicking on the "magnifying glass" icon in the top right corner of the interface.

```
void setup() {
  Serial.begin(9600);
}

void loop() {
  Serial.println("Hello World");
  delay(500);
}
```

## Counter

```
int cnt = 0;

void setup() {
    Serial.begin(9600);
}

void loop() {
    Serial.println(cnt);
    cnt = cnt+1;
    delay(500);
}
```

## Counter up to 20

Version using the modulo (`%`) operation:

```
int cnt = 0;

void setup() {
    Serial.begin(9600);
}

void loop() {
    Serial.print("Counter: ");
    Serial.println(cnt);
    cnt = (cnt+1)%20;
    delay(500);
}
```

Version using a condition (`if`):

```
int cnt = 0;

void setup() {
    Serial.begin(9600);
}

void loop() {
    Serial.print("Counter: ");
    Serial.println(cnt);
    cnt = (cnt+1);
    if(cnt == 10){ 
        cnt = 0;
    }
    delay(500);
}
```
