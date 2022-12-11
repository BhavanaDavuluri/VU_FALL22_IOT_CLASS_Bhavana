Fix the DHT11 sensor on the breadboard and connect jumpwires from breadboard to raspberry pi using below circuit diagram and also connect ohm resistor

![circuit diagram](https://user-images.githubusercontent.com/112037009/193214445-3f4b84ae-f825-4f49-b712-8af9e654c3ae.png)

Login to the dietpi using ssh dietpi@Ipaddress and enter password

Clone and Install the wiringPi

Use the command cd wiringPi to enter to the directory.If not exists then create by using mkdir wiringPi

Then build it by using the command ./build

Then write a program in wiringPi by using nano command

Check and install git by using the following commnad

sudo apt-get install git-core

Then give cd wiringPi

Pull origin by using  git pull origin

Update the code if necessary

To compile the program use gcc -o example example.c -lwiringPi -lwiringPiDev

To run the program use sudo ./example

Then we will get the ouput as Data not good,Skip

Then Update the counter from 16 to 50

Output is as below

![OUTPUT IMAGE](https://user-images.githubusercontent.com/112037009/193214650-b86d7531-a839-4170-b037-6db51d6ed6a3.png)

![Temperature](https://user-images.githubusercontent.com/112037009/206887801-1b100c95-b27e-407b-b87c-853015e499e7.jpg)



