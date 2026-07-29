## Radom Note Generator Assignment

* Write a program that generates random note names and displays them in the Serial Monitor.
* The display speed of the notes may be constant or variable (your choice).
* Hint: the [`random()`](https://www.arduino.cc/reference/en/language/functions/random-numbers/random/) function may be useful ;).
* You must complete this assignment before the next session (during which a solution will be given).
* This assignment is not graded.

<!--
### Possible solution

```
char *notes[] = {"Do","Re","Mi","Fa","Sol","La","Si"};

void setup() {
  Serial.begin(9600);
}

void loop() {
  int randVal = random(7);
  Serial.println(notes[randVal]);
  delay(500);
}
```
-->
