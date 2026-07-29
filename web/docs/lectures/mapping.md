# Mapping and Buying Stuff

## Mapping Techniques

* Sometimes the signal produced by a sensor does not span the entire range of the Arduino/Teensy analog input. For example, the values obtained may be between 234 and 769 instead of 0 and 1023. In this case, the range can be corrected using a cross-multiplication:

```
int sensorValue = analogRead(A0);
int scaledValue = (sensorValue - 234)*1023/(769-234);
```

* In practice, it is rare in this kind of situation for the minimum and maximum sensor values to be stable (e.g., the minimum value may fluctuate between 225 and 240 in the previous example). In this case, the sensor range can be "tightened" and clipped using the `min` and `max` functions:

```
int sensorValue = analogRead(A0);
int scaledValue = max(0,min(1024,(sensorValue - 245)*1023/(760-245)));
```

## Filtering

* It is sometimes necessary to filter values produced by some sensors to stabilize them. These filtering operations can be carried out directly on the target platform (e.g., in Faust using the `si.smoo` or `si.smooth` functions).
* This type of operation can be performed directly on the Arduino using a "normalized integrator" type filter:

$$
y(n) = (1-a_{1})x(n) + a_{1}y(n-1)
$$

where \(a_{1}\) is the pole of the filter (a value of 0.99 is recommended).

## Where to Buy Electronic Components and Materials?

* If you’re in a hurry, want a very large (too large) selection, flawless customer service, and don’t mind paying a bit more: [https://fr.farnell.com/](https://fr.farnell.com/)
* If you want the essentials and are looking for pre-assembled boards: [https://www.mouser.fr/](https://www.mouser.fr/) or [https://www.digikey.fr](https://www.digikey.fr)
* If you want to buy in bulk and pay less with a limited selection: [https://www.amazon.fr/](https://www.amazon.fr/)
* If you want unlimited choice, pay 4 times less, and have a 50% chance of getting a counterfeit: [https://www.aliexpress.com/](https://www.aliexpress.com/)
* For raw materials, you can go to any hardware store (in Sté, I personally prefer Leroy Merlin).
