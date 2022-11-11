Login to dietpi using ssh dietpi@address and by entering password and setup all the devices

Check whether the compiler has installed gcc -v

If not present,install it by using the following command sudo dietpi-software`

Install all the libraries to build Anjay by using the below command

sudo apt-get install git build-essential cmake libmbedtls-dev zlib1g-dev

Now clone the avs_commons by using

cd ~/projects

git clone https://github.com/AVSystem/avs_commons

Now build and install the avs_commons library by using

cd ~/projects/avs_commons

cmake . && make && sudo make install

Retreive the Anjay Code by using the below commands

cd ~/projects

git clone https://github.com/AVSystem/Anjay

Now build the anjay code by using 

cd ~/projects/Anjay
git submodule update --init
cmake . -DDTLS_BACKEND="mbedtls"
make -j

Open Leshan server and continue the process

Install all the Anjay Library objects by 

cd ~/projects/Anjay
cmake -DCMAKE_INSTALL_PREFIX=/home/dietpi/projects/Anjay-esp32-client . && make &&  make install

If the above build doesnot work use the below commands

cd projects
git clone --recurse-submodules --remote-submodules https://github.com/pschragger/Anjay-esp32-client

Move the Anjay-esp32-client directory that was clones earlier 

cd ~/projects/Anjay-esp32-client

Setup the local environment variables by using

cd ~/projects/Anjay-esp32-client
. $HOME/esp/esp-idf/export.sh
idf.py set-target esp32 

Setup the device requirements by using

cd ~/projects/Anjay-esp32-client
idf.py menuconfig

Now the blue screen will popup on command prompt

We need to go to the Components and select Anjay-esp32-client option

Now go to client and enter the server address as shown in leshan server (example coap:addr:5684) and select security mode as non-secure connection

![Screenshot 2022-10-29 235653](https://user-images.githubusercontent.com/112037009/201416972-04449d34-f9a0-47bd-8186-012ebabee095.png)

Now go to Board options and select push button and enter the number as in jump wire to the push button pin as shown below

![Screenshot 2022-11-04 234215](https://user-images.githubusercontent.com/112037009/201428829-669fe5d1-a439-4b0b-9898-1cf69a969809.png)

Now go to connection configuration and enter the ssid and password as shown below

![Screenshot 2022-10-29 235938](https://user-images.githubusercontent.com/112037009/201418728-c4d53100-c762-4cef-bacb-7f74a5a2e96c.png)

Now again we need to build the code for esp-32 by using 

 cd ~/projects/Anjay-esp32-client
 idf.py build
 
 Flash the device by using
 
 ls -l /dev/ttyUSB*
 
 Give the below commands for flashing of the esp-32
 
cd ~/projects/Anjay-esp32-client
sudo chmod 666 /dev/ttyUSB0
idf.py -p 0 flash

Now you have to see esp-32 as client in leshan server



Now click on the esp-32 and you can see push button option as shown below






