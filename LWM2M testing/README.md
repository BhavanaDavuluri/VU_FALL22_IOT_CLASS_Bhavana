This file contains the description how to install the leshan server and some important screenshots about the sessions. While building leshan by entering mvn clean install, I got the Build Failure. The error shows about heap memory and heap space. So, I used the command export MAVEN_OPTS=â-Xmx512mâ and set MAVEN_OPTS=â-Xmx512mâ to extend the heap memory. So, after completing this step I entered mvn clean install. Then I got Build Success and followed the next steps to the leshan server. <br>

It also contains information about the bootstrap service/client test and important screenshots about the sessions and about how we use wireshark to analyze protocols

For more information visit https://github.com/BhavanaDavuluri/VU_FALL22_IOT_CLASS_Bhavana/blob/main/LWM2M%20testing/LESHAN_INSTALLATION.md
