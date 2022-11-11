Login to dietpi using ssh dietpi@address and by entering password

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

Now go to the board options and select light control

![Screenshot 2022-10-29 235721](https://user-images.githubusercontent.com/112037009/201417624-ff32eb9c-3282-4f03-be5a-ec2a2ed61418.png)

Now go to Light control options as shown in the above figure and select enable red colour and give the number in red color pin according to your jump wire

![Screenshot 2022-10-30 004625](https://user-images.githubusercontent.com/112037009/201418164-bee80fc5-52d5-4751-afb4-d7ef5c459769.png)

Now go to connection configuration and enter the ssid and password as shown below

![Screenshot 2022-10-29 235938](https://user-images.githubusercontent.com/112037009/201418728-c4d53100-c762-4cef-bacb-7f74a5a2e96c.png)






 
