# Diy-Pickcrafter-Using-Arduino

![Screenshot (1016)](https://user-images.githubusercontent.com/118633170/230844141-d5fcb081-51ac-47ff-9e69-bfb21c7adc97.png)


If you have hard-time 3d printing stuff and other materials which i have provided in this project please refer the professionals for the help, [JLCPCB](https://jlcpcb.com/RNA) is one of the best company from shenzhen china they provide, PCB manufacturing, PCBA and 3D printing services to people in need, they provide good quality products in all sectors

[JLCPCB](https://jlcpcb.com/RNA)


Please use the following link to register an account in [JLCPCB](https://jlcpcb.com/RNA)

https://jlcpcb.com/RNA


Pcb Manufacturing

----------

2 layers

4 layers

6 layers

jlcpcb.com/RNA



PCBA Services

[JLCPCB](https://jlcpcb.com/RNA) have 350k+ Components In-stock. You don’t have to worry about parts sourcing, this helps you to save time and hassle, also keeps your costs down.

Moreover, you can pre-order parts and hold the inventory at [JLCPCB](https://jlcpcb.com/RNA), giving you peace-of-mind that you won't run into any last minute part shortages. jlcpcb.com/RNA

3d printing

-------------------

SLA -- MJF --SLM -- FDM -- & SLS. easy order and fast shipping makes [JLCPCB](https://jlcpcb.com/RNA) better companion among other manufactures try out [JLCPCB](https://jlcpcb.com/RNA) 3D Printing servies

[JLCPCB](https://jlcpcb.com/RNA) 3D Printing starts at $1 &Get $54 Coupons for new users
![Screenshot (1017)](https://user-images.githubusercontent.com/118633170/230844189-79e06dcc-82a4-44b3-86ac-e3131de8ae14.png)
![Screenshot (1018)](https://user-images.githubusercontent.com/118633170/230844196-24f6b0a8-87e6-4dac-a117-dda51539ead6.png)
![Screenshot (1020)](https://user-images.githubusercontent.com/118633170/230844179-900d4358-df32-4fed-b2f1-5d085012b694.png)


The capacitiveSensor library turns two or more Arduino pins into a capacitive sensor, which can sense the electrical capacitance of the human body. All the sensor setup requires is a medium to high value resistor and a piece of wire and a small (to large) piece of aluminum foil on the end. At its most sensitive, the sensor will start to sense a hand or body inches away from the sensor.

Version 04 adds support for Arduino 1.0, and fixes an obscure possible race condition with Tone, Servo and other libraries that perform I/O in interrupt context.

Version 03 has been updated to C++ and supports multiple inputs. It also includes some utility functions to make it convenient to change timeout values

Capacitive sensing may be used in any place where low to no force human touch sensing is desirable. An Arduino and the library may be used to sense human touch through more than a quarter of an inch of plastic, wood, ceramic or other insulating material (not any kind of metal though), enabling the sensor to be completely visually concealed.

A capacitive sensor covered with paper or other insulator also acts as fairly good (human touch) pressure sensor with an approximately logarithmic response. In this regard it may surpass force sensing resistors in some applications


The capacitiveSensor method toggles a microcontroller send pin to a new state and then waits for the receive pin to change to the same state as the send pin. A variable is incremented inside a while loop to time the receive pin's state change. The method then reports the variable's value, which is in arbitrary units.

The physical setup includes a medium to high value (100 kilohm - 50 megohm) resistor between the send pin and the receive (sensor) pin. The receive pin is the sensor terminal. A wire connected to this pin with a piece of foil at the end makes a good sensor. For many applications, a more useful range of values is obtained if the sensor is covered with paper, plastic, or another insulating material, so that users do not actually touch the metal foil. Research has shown that a small capacitor (100 pF) or so from sensor pin to ground improves stability and repeatability.

When the send pin changes state, it will eventually change the state of the receive pin. The delay between the send pin changing and the receive pin changing is determined by an RC time constant, defined by R * C, where R is the value of the resistor and C is the capacitance at the receive pin, plus any other capacitance (e.g. human body interaction) present at the sensor (receive) pin. Adding small capacitor (20 - 400 pF) in parallel with the body capacitance, is highly desirable too, as it stabilizes the sensed readings.

![Screenshot (1023)](https://user-images.githubusercontent.com/118633170/230844270-b276e46f-c02b-4c47-81c4-48c12b6381f9.png)
![Screenshot (1021)](https://user-images.githubusercontent.com/118633170/230844295-9d907b2c-9a97-4f88-99bb-08c0cb2fcb5b.png)
![Screenshot (1022)](https://user-images.githubusercontent.com/118633170/230844312-6ddd3537-a4a3-44bb-8b0b-1ff4e424c09d.png)

The library contains three main methods and some utility methods:

CapacitiveSensor CapacitiveSensor(byte sendPin, byte receivePin)
CapacitiveSensor creates an instance of the library (please note the capital letters, this is not the same method as below)

long capacitiveSensorRaw(byte samples)
capacitiveSensorRaw requires one parameter, samples, and returns a long integer containing the absolute capacitance, in arbitrary units. The samples parameter can be used to increase the returned resolution, at the expense of slower performance. The returned value is not averaged over the number of samples, and the total value is reported.

capacitiveSensorRaw will return -2 if the capacitance value exceeds the value of CS_Timeout_Millis (in milliseconds). The default value for CS_Timeout_Millis 2000 milliseconds (2 seconds).

long capacitiveSensor(byte samples)
capacitiveSensor requires one parameter, samples, and returns a long containing the added (sensed) capacitance, in arbitrary units. capacitiveSensor keeps track of the lowest baseline (unsensed) capacitance, and subtracts that from the sensed capacitance, so it should report a low value in the unsensed condition.

The baseline is value is re-calibrated at intervals determined by CS_Autocal_Millis. The default value is 200000 milliseconds (20 seconds). This re-calibration may be turned off by setting CS_Autocal_Millis to a high value with the set_CS_AutocaL_Millis() method.

void set_CS_Timeout_Millis(unsigned long timeout_millis);
The set_CS_Timeout_Millis method may be used to set the CS_Timeout_Millis value, which determines how long the method will take to timeout, if the receive (sense) pin fails to toggle in the same direction as the send pin. A timeout is necessary because a while loop will lock-up a sketch unless a timeout is provided. CS_Timeout_Millis' default value is 2000 milliseconds (2 seconds).

void reset_CS_AutoCal()
reset_CS_AutoCal may be used to force an immediate calibration of capacitiveSensor function.

void set_CS_AutocaL_Millis(unsigned long autoCal_millis)
The method set_CS_AutocaL_Millis(unsigned long autoCal_millis) may be used to set the timeout interval of the capacitiveSensor function. Re-calibration may be turned off by using set_CS_AutocaL_Millis to set CS_AutocaL_Millis to "0xFFFFFFFF".

![Screenshot (1028)](https://user-images.githubusercontent.com/118633170/230844414-3ac841b8-add7-49a3-8726-4c947ffbef1f.png)
![Screenshot (1024)](https://user-images.githubusercontent.com/118633170/230844427-c71fc031-9f34-40e5-aca5-8d692b9e15de.png)
![Screenshot (1025)](https://user-images.githubusercontent.com/118633170/230844437-180b0c71-e043-4db4-b42d-cee051cd167c.png)


Grounding and other known issues
The grounding of the Arduino board is very important in capacitive sensing. The board needs to have some connection to ground, even if this is not a low-impedance path such as a wire attached to a water pipe.

Capacitive sensing has some quirks with laptops unconnected to mains power. The laptop itself tends to become sensitive and bringing a hand near the laptop will change the returned values.

Connecting the charging cord to the laptop will usually be enough to get things working correctly. Connecting the Arduino ground to an earth ground (for example, a water pipe) could be another solution.

Another solution that seems to have worked well on at least one installation, is to run a foil ground plane under the sensor foil (insulated by plastic, paper, etc.), and connected by a wire to ground. This worked really well to stabilize sensor values and also seemed to dramatically increase sensor sensitivity.

Scroll Wheels (well, slide pots anyway)
Experiments with a slide pot type linear sensor have been successful with just two pins and a resistance ladder. The basic layout is shown in the Quantum Scrollwheel sensor datasheet.

The code uses this type of arrangement

CapacitiveSensor Left32  = CapacitiveSensor(3, 2); // wire from pin 2 to left side of resistor ladder\
CapacitiveSensor Right23 = CapacitiveSensor(2, 3); // wire from pin 3 to right side of resistor ladder
Where the pins switch their send and receive positions. With a linear resistance ladder, a finger closer to the send pin will report lower values because resistance downstream from the capacitance is basically out of the circuit.

So in this manner when a finger is moved from one pin to the other the two calls to capacitiveSensorRaw will report complementary values that have an approximately constant value to them. The complication comes in when trying to deal with how much contact (capacitance) is present, which raises (or lowers) both values, but not necessarily in a linear manner.

![Screenshot (1026)](https://user-images.githubusercontent.com/118633170/230844456-43f2ada6-da41-4492-83ed-d7f8def14c66.png)
![Screenshot (1027)](https://user-images.githubusercontent.com/118633170/230844475-9675d369-8ad5-4e33-9c49-f14afe14f8e4.png)

At some point I'll get the sketch posted here.

Error Messages
capacitiveSensor and capacitiveSensorRaw will return -1 with an invalid choice of pin parameter, but it appears that this feature is not working at this writing. Engineers are working on this, stand by...

capacitiveSensor and capacitiveSensorRaw will return -2 if the methods timeout. This is caused by the count exceeding the value of CS_Timeout_Millis, which is set at a default value of 2000 milliseconds (2 seconds). This is most often caused by a missing resistor or the resistor in the wrong pin. It could also be caused by a sensor that is grounded or connected to +5 V.


ouch screens have become an increasingly popular input method over the last decade, and it’s easy to see why. Touch inputs allow users to employ their fingers to interact with an electronic device. This leads to input methods that are very easy to understand, and even children can quickly understand them and learn how to interact with an electronic device. This article discusses two ways of adding capacitive touch inputs to any of your Arduino-based DIY projects.

Capacitive sensors are proximity sensing devices that can detect a user’s finger, for example, without the need for physical contact. Prominent examples are touch screens and various touch controls - one popular recent example is on modern cooktops. However, that’s just a handful of visible applications. Capacitive sensors can be hidden in other devices so that they aren’t inherently visible to the user.

As the name implies, a capacitive sensor acts like a simple capacitor. A piece of metal internally connects to an oscillator circuit. Unlike a pre-built capacitor, the target to be sensed (for example, a user’s finger) acts as the second plate of the capacitive sensor. In this article, an Arduino takes the role of the previously mentioned oscillator circuit. The Arduino periodically sends out pulses and measures how much time elapses until it receives a response. When the target comes closer to the piece of metal that forms the first plate of the sensor, the Arduino can detect a change in the timing and use that information to determine whether a user made a touch input.

Note that this is a short and simplified description of the working principle of such a sensor. Furthermore, many aspects determine how well the sensing works - two of which are the size of the first metal plate and the surface area of the target object.

![Screenshot (1030)](https://user-images.githubusercontent.com/118633170/230844666-b40af1c3-7fb2-4bc1-96af-06360ae4ebf2.png)
![Screenshot (1029)](https://user-images.githubusercontent.com/118633170/230844686-895cd1e4-4eee-47e4-97db-f0c69c2a484d.png)


Capacitive Sensing


We only need a conductive object to form one plate of the sensor, an Arduino, a relatively large value resistor, and a few jumper wires to build a simple capacitive proximity sensor. The resistor connects D2 and D12 of the Arduino. Additionally, pin D2 also connects one side of the resistor to a metal object such as a paperclip, a piece of aluminum foil, or a tool:

his method already yields rather good results. It, however, sometimes also delivers wrong results and somewhat inaccurate readings. This simple approach might be alright for scenarios where, for example, you only want to sense whether a user brings his or her finger close enough to the sensor to activate it. The previously discussed method heavily depends on many factors such as the size of the plate and the temperature.

Dedicated touch and proximity sensoare a great way to guarantee consistent sensor readings in many applications. Therefore, these sensor boards are a sensible alternative to the simple homemade experimental approach discussed above. The downsides of such external sensor modules are the increased size, complexity, and higher price. Therefore, you have to carefully evaluate what the most important aspects of your project are and what you’d like to focus on.

Summary
Capacitive proximity and touch sensors represent great for adding engaging and intuitive input options to DIY projects. As the name suggests, a capacitive sensor is nothing more at its core than a simple capacitor. One plate of the capacitor consists of a fixed conductive object, such as a metal strip. A target object, such as a user’s finger, forms the other plate. An Arduino sends out pulses and measures how long it takes until the software reports a response. The Arduino can then translate this delay to a proximity value. In its simplest form, a home-made sensor can deliver good results when tweaked appropriately for some applications. A dedicated proximity sensor board can achieve better results. Choosing to add an additional board, however, also increases the overall size, complexity, and cost of a project.

![Screenshot (1036)](https://user-images.githubusercontent.com/118633170/230844768-301f7913-1bfc-4aad-8e8a-3db8536c92bf.png)
![Screenshot (1033)](https://user-images.githubusercontent.com/118633170/230844750-db594f11-dca4-45fe-ba6b-b8fd0ad33346.png)

To create a touch sensor on an Arduino board. You will need a resistor and a cable and/or conductive paint. The resistor connects the measuring pin with the reference pin and the cable runs from the measuring pin to a sheet of aluminum foil, conductive paint or other material. The value of the resistance will define the sensitivity of the sensor. The higher the resistance value, the more the sensor will be able to detect an object from a distance. We use a resistance of 1MOhm but you can choose the most suitable for your application between 500k and 40Mohm.

There are microcontrollers such as the NodeMCU (ESP8266 or ESP32) with integrated touch sensors. In this case, a single conductor connected to the pin is sufficient to create a capacitive sensor.#include <CapacitiveSensor.h>//https://github.com/PaulStoffregen/CapacitiveSensor

//Parameters
bool autocal  = 0;
const int numReadings  = 10;
long readings [numReadings];
int readIndex  = 0;
long total  = 0;
const int sensitivity  = 1000;
const int thresh  = 200;
const int csStep  = 10000;
CapacitiveSensor cs  = CapacitiveSensor(2, 3);

void setup() {
  //Init Serial USB
  Serial.begin(9600);
  Serial.println(F("Initialize System"));
  //Init cs
  if (autocal == 0) {
    {
      cs.set_CS_AutocaL_Millis(0xFFFFFFFF);
    }
  }
}

void loop() {
  Serial.println(smooth());
}

long smooth() { /* function smooth */
  ////Perform average on sensor readings
  long average;
  // subtract the last reading:
  total = total - readings[readIndex];
  // read the sensor:
  readings[readIndex] = cs.capacitiveSensor(sensitivity);
  // add value to total:
  total = total + readings[readIndex];
  // handle index
  readIndex = readIndex + 1;
  if (readIndex >= numReadings) {
    readIndex = 0;
  }
  // calculate the average:
  average = total / numReadings;

  return average;
}


A capacitive sensor works like an antenna that generates an electric field. When a material gets close to the antenna, it will change the capacity of this field. The microcontroller senses this difference and can determine the proximity of the object. With this technology, it is possible to transform any conductive object into a sensor

![Screenshot (1031)](https://user-images.githubusercontent.com/118633170/230844715-56ac6fad-49e6-40fb-9b3d-104cb9491abf.png)
![Screenshot (1032)](https://user-images.githubusercontent.com/118633170/230844728-4f963ec2-d1d6-43ef-8bf2-75c58be075e4.png)



First, you need to paint your sensor with Electric Paint. Try to make it approximately the size of your hand to start. The outer shape isn't important, but the total amount Now you have explored capacitive touch and proximity sensing, you can design your very own touch sensor and proximity sensors. The sensors do not need to be square. Experiment with your own designs and see how this impacts the sensitivity of the system. Proximity sensing is also quite dependent on the design of the sensor. We have written our design rules for creating a sensor and the Printed Sensors are ideal for proximity sensing.

Capacitive sensing with the Arduino is very limited. The capacitive sensor is easily influenced by electrical noise and changes in the environment, such as humidity. To adjust the sensor requires constant calibration. We designed the Touch Board to solve these problems  of Electric Paint is. Too big, and it may be too unstable, too small, and it might not work. You can try painting a few different designs to compare their performance. You can paint it on any non-conductive surface, like the paper we used here. Leave your sensor pad to dry.

![Screenshot (1034)](https://user-images.githubusercontent.com/118633170/230844760-d9341b03-413b-485a-9b81-5acea092eef4.png)
![Screenshot (1035)](https://user-images.githubusercontent.com/118633170/230844765-49a3d896-dd5a-49eb-b729-0e86380e9b5c.png)

