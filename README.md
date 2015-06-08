# MinecarftServer-Bukkit-Forge-Ubuntu
A Minecraft server pack based on Ubuntu Linux OS with Bukkit and Forge support

This is a convenient server pack for MinecraftServer kickstarter to build its environment on Ubuntu System(Also supprt Debian). You should install Java on your Ubuntu server first following the steps below.

# Step One

*Run java -v in your command line.*

If you get java: command not found (which may be followed by more text) or if you do have another Java version than 1.6 then you need to install or update java. The official Oracle Java is recommended. A few individuals have experienced issues with OpenJDK. Others report that running on OpenJDK is completely fine.
### Debian

Ensure that the non-free repository is being scanned by apt. You do this by adding non-free to your /etc/apt/sources.list file. e.g.:

* deb http://ftp.uk.debian.org/debian/ squeeze main contrib non-free

Update your sources list (as root):

* apt-get update

Then to install Java, simply type this in terminal and press enter (as root):

* apt-get install sun-java6-jre

### Ubuntu

Unfortunately, some licensing issues have prevented Canonical from allowing repositories to have Sun Java, so you must either download it directly from Oracle, package it, and install it or you could use the PPA provided by webupd8 by following the instructions below.

This guide has been tested on Ubuntu Server 12.10.

Note: You might need to install the package "software-properties-common" by running apt-get install software-properties-common and/or "python-software-properties" by running apt-get install python-software-properties to use the apt-add-repository command.

Run the following commands in this order to add the PPA, update the source list and then install java:

* sudo apt-add-repository ppa:webupd8team/java
* sudo apt-get update
* sudo apt-get install oracle-java7-installer

Then run this to check what version you have installed:
java -version

The output should be similar to:

* java version "1.7.0_10"
* Java(TM) SE Runtime Environment (build 1.7.0_10-b18)
* Java HotSpot(TM) 64-Bit Server VM (build 23.6-b04, mixed mode)

# Step Two

Get the repository to your server, run the command below:

* java -Xmx1G -Xms1G -jar cauldron-1.7.10-1.1388.1.0-server.jar nogui