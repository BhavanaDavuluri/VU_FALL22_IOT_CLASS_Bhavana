Connect the DHT11 sensor on the breadboard and connect all the jumpwires as shown in the circuit diagram.

![Aurdino Circuit](https://user-images.githubusercontent.com/112037009/193188123-f3398c9b-5bec-41c4-9cb1-9e2cd7f88516.png)

Install the Arduino from the https://www.arduino.cc/en/software

Now got File->Preferences in Arduino IDE and enter the URL https://dl.espressif.com/dl/package_esp32_index.json in Additional Boards Manager

Now go to Tools->Board->Boards Manager and then check for esp32 and install ESP32 by Espressif Systems

Now go to Tools->Board and then check for esp32 and select ESP32 Wrover Module

And Later connect ESP32 to the breadboard and connect usb to the laptop

Go to Tools and check for Port and select COM4

Download the DHTesp file from https://github.com/beegee-tokyo/DHTesp

After downloading we need to go to Sketch->Include Library->Add  .Zip Library and select the downloaded DHTesp file

In library open C and then open C_Tutorial and copy the code from page 271  and save the code as a.ino

Now select the Right Arrow at the left Corner of the Arduino and then compile it

After successful compilation, upload the code

After uploading the code, Select Serial Monitor 

Now change the baud rate to 115200

Then you can see the temperature and humidity as follows

![aurdenio output](https://user-images.githubusercontent.com/112037009/193188483-039fb03b-a572-4021-bdd6-e066d457772e.png)


