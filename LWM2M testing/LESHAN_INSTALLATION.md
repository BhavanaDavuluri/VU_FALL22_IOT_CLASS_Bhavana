Installation of Leshan Server:

Login to the dietpi by entering the ip address and password. The command to enter ip address is 
ssh dietpi@(IPADDR_OF_PI)
![Login](https://user-images.githubusercontent.com/112037009/192080503-e2603c69-586d-4264-abeb-2a18a5363a50.png)

To download the software git and java we need to use the command sudo dietpi-software.

Then we search for git and then select - Git: Clone and manage Git repositories locally and then press  install. 

After the installation of git check the version by git –version command.

Similarly, we need to install java jdk by entering sudo dietpi-software and search for java jdk.

Select - Java JDK: OpenJDK Development Kit and then press install. 

After the installation of java check its version by java –version.

Now we need to create a directory for download by using command mkdir download.Then change the directory to download by typing cd download.

Now we need to download the maven tarball by entering wget https://dlcdn.apache.org/maven/maven-3/3.8.6/binaries/apache-maven-3.8.6-bin.tar.gz

And now unpack the tarball tar xzvf apache-maven-3.8.6-bin.tar.gz

Now add the bin directory to the path by echo 'PATH="${PATH}:~/download/apache-maven-3.8.6/bin"' >>  ~/.bashrc

Enter bash and then mvn -v to check the installation

The path to set the  java environment variable is sudo echo 'JAVA_HOME="/usr/lib/jvm/java-17-openjdk-arm64"' >> ~/.bashrc

Enter bash and then echo $JAVA_HOME to check the installation

Enter cd and then create a directory as mkdir projects and then cd projects. And then enter the command git clone https://github.com/eclipse/leshan.git

Now enter cd ~/projects/leshan and then mvn clean install. Then we will get Build Success as shown in figure below

![BuildSuccess](https://user-images.githubusercontent.com/112037009/192080907-8082a74f-248c-47b3-800a-29f4f2be6c4a.png)

Now we need to test the server using java -jar leshan-server-demo/target/leshan-server-demo-*-SNAPSHOT-jar-with-dependencies.jar &

Open the web page and enter  http://RPI_IPADDR:8080 which will direct to the leshan server 

Now if we run the command  java -jar leshan-client-demo/target/leshan-client-demo-*-SNAPSHOT-jar-with-dependencies.jar  in command prompt the dietpi will be displayed in the leshan server

![leshanserver](https://user-images.githubusercontent.com/112037009/192080883-5fb960ca-58b9-47ba-adf6-d0e47f7e2d12.png)

![leshan client](https://user-images.githubusercontent.com/112037009/192080888-8dc0e793-6c41-4e09-bdbf-926d3ce6bd14.png)


Bootstrap service/client 

Login to the dietpi by entering the ip address and password. The command to enter ip address is ssh dietpi@(IPADDR_OF_PI)

To download the software git and java we need to use the command sudo dietpi-software

Then we search for git and then select - Git: Clone and manage Git repositories locally and then press install 

After the installation of git check the version by git –version command

Similarly, we need to install java jdk by entering sudo dietpi-software and search for java jdk

select - Java JDK: OpenJDK Development Kit and then press install. After the installation of java check its version by java –version

Now we need to create a directory for download by using command mkdir download

Now change the directory to download by typing cd download

Now we need to download the bootstrap server by entering wget https://ci.eclipse.org/leshan/job/leshan/lastSuccessfulBuild/artifact/leshan-bsserver-demo.jar

And then enter java -jar ./leshan-bsserver-demo.jar and do ctrl + C to exit

Enter bash and then mvn -v to check the installation

The path to the java environment variable is sudo echo 'JAVA_HOME="/usr/lib/jvm/java-17-openjdk-arm64"' >> ~/.bashrc

This is the path to the java environment variable

Enter bash and then echo $JAVA_HOME to check the installation

Enter cd and then create a directory as mkdir projects and then cd projects. And then enter the command git clone https://github.com/eclipse/leshan.git

Now enter cd ~/projects/leshan and then mvn clean install. Then we will get Build Success as shown in figure below

![bootstrap build success](https://user-images.githubusercontent.com/112037009/192081008-4dfbc82d-2919-4767-b28b-1a69df4c0f0e.png)

Now we need to test the server using java -jar leshan-bsserver-demo/target/leshan-bsserver-demo-*-SNAPSHOT-jar-with-dependencies.jar

Open the web page and enter  http://RPI_IPADDR:8080 which will direct to the leshan bs server  demo as

![bootstrap leshan](https://user-images.githubusercontent.com/112037009/192081040-96ecf50e-12f2-40e2-905e-61569b7fb8c5.png)

On the right side of the leshan there will pop up a add configuration, we need to click that

![client configuration](https://user-images.githubusercontent.com/112037009/192081075-07b42609-9382-4f66-b9f3-797365021d59.png)

Here you need to add the name as your choice and click next

![identikty](https://user-images.githubusercontent.com/112037009/192081085-30953cc0-fffb-4d33-94ea-8e5ffb7d56d8.png)

After clicking next this page will open and select Using (D)TLS and you need to enter the identity and key is the hexadecimal version of the identity.

By clicking next it will add the configuration and the image is 

![finalbootstrap](https://user-images.githubusercontent.com/112037009/192081098-9db0420b-0ad1-43c7-a051-6e0f529693bc.png)



Using wireshark to analyze protocols

In your system download the wireshark and all the setup wizards.

Open Wire Shark and then select the Wi-Fi network and search for http and then click enter.

You can see a series of networks as shown in figure. In this way we analyze the protocols

![wiresharks](https://user-images.githubusercontent.com/112037009/192081126-a894fc85-10d5-405b-a778-25d1b3338481.png)







