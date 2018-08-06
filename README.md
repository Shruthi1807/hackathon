# hackathon
PROJECT


INTRODUCTION


The project that we are going to concentrate on is for the benefit of the people of the society and their welfare. This device is going to be fixed above the door, where the data and instructions would be already fed to it. 


PRINCIPLE


The main objective of this project is to  make people to carry all their important belongings that are required when they leave the house rather than forgetting it and suffering.
 further instructions to be added , an artificial intelligence will be created specially to connect to this device. So that the things to be remembered can be intimated to the device through it.


WORKING


Initially, when a person leaves the house through the door, he or she is fully scanned, and checked whether they are carrying the necessary items that were fed to the device. If yes, the AI would greet the master for their day. Otherwise, the device either gives  a message of what they have forgotten 
through the display mode or a voice note, informing the person about their daily


ADVANTAGE

The main advantage is people who lack in memory power and people who are heavily loaded with work tension tend to forget things easily. It also plays an excellent role for people who leaves out of town for vacation, for the students when they leave for school and also for people who are working. But I will assure you that if this project becomes a success people would be benefited to a large extent and I am sure that it would be used by every single person in this world or already within India.

CONCLUSION


People might ask for the purpose of remainders in mobiles, but what if you forget you mobile itself or if you phone is in silent. There are chances right. And if there are people who think like that, then by now Google home would haven't been available or successfully launched even after the availability of the mobile and internet to search for the informations. It is same as that. It is just to make our life better and easier.


basic coding for any port scanner can be:












#!/usr/bin/env python
import socket
import subprocess
import sys
from datetime import datetime

# Clear the screen
subprocess.call('clear', shell=True)

# Ask for input
remoteServer    = raw_input("Enter a remote host to scan: ")
remoteServerIP  = socket.gethostbyname(remoteServer)

# Print a nice banner with information on which host we are about to scan
print "-" * 60
print "Please wait, scanning remote host", remoteServerIP
print "-" * 60

# Check what time the scan started
t1 = datetime.now()

# Using the range function to specify ports (here it will scans all ports between 1 and 1024)

# We also put in some error handling for catching errors

try:
    for port in range(1,1025):  
        sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        result = sock.connect_ex((remoteServerIP, port))
        if result == 0:
            print "Port {}: 	 Open".format(port)
        sock.close()

except KeyboardInterrupt:
    print "You pressed Ctrl+C"
    sys.exit()

except socket.gaierror:
    print 'Hostname could not be resolved. Exiting'
    sys.exit()

except socket.error:
    print "Couldn't connect to server"
    sys.exit()

# Checking the time again
t2 = datetime.now()

# Calculates the difference of time, to see how long it took to run the script
total =  t2 - t1

# Printing the information to screen
print 'Scanning Completed in: ', total
