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

[BuildSuccess](https://user-images.githubusercontent.com/112037009/192080747-80b28e7c-e32e-4d0a-927b-8160a9b1d3ae.png)

Now we need to test the server using java -jar leshan-server-demo/target/leshan-server-demo-*-SNAPSHOT-jar-with-dependencies.jar &

Open the web page and enter  http://RPI_IPADDR:8080 which will direct to the leshan server 

Now if we run the command  java -jar leshan-client-demo/target/leshan-client-demo-*-SNAPSHOT-jar-with-dependencies.jar  in command prompt the dietpi will be displayed in the leshan server

![leshanserver](https://user-images.githubusercontent.com/112037009/192080883-5fb960ca-58b9-47ba-adf6-d0e47f7e2d12.png)

![leshan client](https://user-images.githubusercontent.com/112037009/192080888-8dc0e793-6c41-4e09-bdbf-926d3ce6bd14.png)



