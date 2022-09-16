The laptop which I am using is HP Laptop - 15t-dy200 SCREEN SIZE15.6", Windows 11 Home, Intel® Core™ i7-1165G7 (up to 4.7 GHz, 12 MB L3 cache, 4 cores) + Intel® Iris® Xe Graphics,16 GB DDR4-2666 SDRAM (2 x 8 GB),256 GB PCIe® NVMe™ M.2 SSD.
The router which I used is GL.iNet GL-MT300N-V2(Mango) Portable Mini Travel Wireless Pocket VPN Router - WiFi Router/Access.


Connect the router to your laptop through cable and setup the router by entering the details of password. Then open http://192.168.8.1/ path in browser and connect to Wi-Fi. The router is setup now.
![image](https://user-images.githubusercontent.com/112037009/190512931-22a77f24-f3e8-49ee-a89e-ba34269e0c12.png)
Now Flash the sd card by using balena. After flashing, remove the sd card and power on the raspberry pi and connect raspberry pi to laptop by using hdmi and connect the raspberry pi with router by wan.
![image](https://user-images.githubusercontent.com/112037009/190513215-0e3bdfd9-ff82-44a1-9bc1-9e56f9091a6f.png)
Keep the sd card in raspberry pi and open dietpi and dietpi_wifi text files and edit the file according to your ssid and location etc.
The changes to be made in dietpi-wifi are 

aWIFI_SSID[0]='IOT-PAS'

aWIFI_KEY[0]='iotlogin'

The changes to be made in dietpi file are
AUTO_SETUP_LOCALE=en_US.UTF-8

AUTO_SETUP_KEYBOARD_LAYOUT=us

AUTO_SETUP_TIMEZONE=America/New_York

AUTO_SETUP_NET_ETHERNET_ENABLED=0

AUTO_SETUP_NET_WIFI_ENABLED=1

AUTO_SETUP_NET_WIFI_COUNTRY_CODE=US

AUTO_SETUP_DHCP_TO_STATIC=1

AUTO_SETUP_NET_HOSTNAME=DietPi_{YOUR_INITIALS}

AUTO_SETUP_HEADLESS=1

AUTO_SETUP_AUTOSTART_TARGET_INDEX=1

SURVEY_OPTED_IN=0

CONFIG_SERIAL_CONSOLE_ENABLE=1

Open command prompt and enter ssh root@ipaddress and password is default as dietpi. The ip address is the address of raspberry pi which is detected in router website in clients.
![image](https://user-images.githubusercontent.com/112037009/190513412-9ee0de6d-83c5-416d-b3fa-a199537c3a49.png)
Some installations and updates will be done. Later it is asked to change the password to new one. User enters the new password. 
![image](https://user-images.githubusercontent.com/112037009/190513465-0ef9417b-621c-463b-b41c-1f656273a7a9.png)

     It also asks to change the password of unix user. Then the user will change the password.
![image](https://user-images.githubusercontent.com/112037009/190513509-d4fd3a72-5746-481c-81f3-6322d0ffb193.png)
Finally the password is changed and now again open command prompt and enter ssh root@ipaddress and the new password .
After completing all this then it displays as Welcome to Dietpi. Finally the raspberry pi is setup.
![image](https://user-images.githubusercontent.com/112037009/190513590-1055aa87-fbec-4bef-ad1a-edb6b7910a3f.png)

