After installing dietpi, you need to download the software by searching them by name.The software need to be installed are MQTT,Node-RED,PostgreSQL.
The screen displays as below for searching
![image](https://user-images.githubusercontent.com/112037009/190516452-c2812cb4-d3f3-4409-b6cb-644e52eb8892.png)
Now After entering all the softwares,the screen will display as below.
![image](https://user-images.githubusercontent.com/112037009/190516502-5228f8f5-cc84-4e1b-82f7-b73c3ca0b102.png)
After downloading all the software, we need to create a database by using commands.

sudo su postgres

The command is to run pi in ssh

After connecting we create database as

Create database test;

Now exit from this by pressing ctrl+d twice.

Now we need to create table as

create table people (name text, company text);

Now insert the values as 

insert into people values ('Ben Nuttall', 'Raspberry Pi Foundation');

insert into people values ('Rikki Endsley', 'Red Hat');

We need to display the values in database.

Select * from people;

![image](https://user-images.githubusercontent.com/112037009/190516976-ceb8bf88-1a5c-44ed-bb04-454fe56fc55d.png)

Now we need to alter the listen address

ALTER SYSTEM SET LISTEN_ADDRESSES = '*';

Now restart the device by clicking Ctrl+D twice

We need to check the log by entering the command.

cat /var/log/postgresql/postgresql-13-main.log

The contents of log are displayed here.

Now we need to connect to Node-RED by entering http://{YOUR_RPI_IPADDRESS}:1880in browser.

Go to Manage Pallet and install node-red-contrib-postgres

Then create the nodes as trigger, template, postgres and debug. It shows as follows.

![image](https://user-images.githubusercontent.com/112037009/190517195-06b3fa71-6277-45ed-b614-3e594517fabb.png)
