# DigitalOcean - PaperMC


![DigitalOcean](https://img.shields.io/badge/DigitalOcean-%230167ff.svg?style=for-the-badge&logo=digitalOcean&logoColor=white) ![Debian](https://img.shields.io/badge/Debian-D70A53?style=for-the-badge&logo=debian&logoColor=white)

A repository containing the configuration files for my Minecraft server.  

![neofetch](neofetch.png)
## Server Information

*   **Minecraft Version:** 1.21.4
*   **Server Type:** PaperMC
*   **Hosting Provider:** DigitalOcean
*   **Hosting machine type:** Droplet

## Machine specifications

*   **CPU:** 4vCPU Premium AMD 3.00Ghz
*   **Memory:** 16GB
*   **Disk space:** 200GB NVMe
*   **Location:** Frankfurt Data Center - 1

## Overview

In here, you will be able to find configuration files for my Minecraft PaperMC 1.21.4 server hosted on DigitalOcean. This setup includes essential plugins for server management, world editing, permissions, player list display, and multi-world support.  

## Plugins Used

*   [EssentialsX](https://essentialsx.net/) - Essential commands and features for server administration and gameplay.
*   [WorldEdit](https://dev.bukkit.org/projects/worldedit) - In-game map editor for building and modification.
*   [LuckPerms](https://luckperms.net/) - A permissions management system.
*   [TAB](https://www.spigotmc.org/resources/tab-1-5-x-1-20-x.57806/) - Advanced player list and scoreboard customization.
*   [Multiverse-Core](https://dev.bukkit.org/projects/multiverse-core) - Multi-world management plugin.

## Configuration Overview

This repository includes configuration files for:

*   `server.properties`: Core server settings.
*   `bukkit.yml`, `spigot.yml`, `paper.yml`: Server performance and behavior tuning.
*   `plugins/Essentials/config.yml`: EssentialsX main configuration.
*   `plugins/LuckPerms/config.yml`: LuckPerms configuration.
*   `plugins/TAB/config.yml`: TAB configuration.
*   `plugins/Multiverse-Core/config.yml`: Multiverse-Core configuration.

## Detailed description

I run everything as a user `mc` on my server in the `/home/mc/mc-serv2` directory. 
I use Secure File Transfer Protocol with Termius to upload necessary `.jar` files to the server, since the `wget` command does not always work.

## Issues

#### Java 21 installation issue

One of the problems I encountered was that I couldn't get `apt` to install the newer version of Java. I needed version 21 to be able to run newer versions of Paper. However, `apt` every time I tried to install it, returned a response stating that there was no package candidate or that there was no package named that. Neither Java Runtime Environment nor Open Java Development Kit wanted to install.
```py
root@debian-s-4vcpu-16gb-amd-fra1-01
▶ ~ # apt install openjdk-21-jdk-headless -y
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
E: Unable to locate package openjdk-21-jdk-headless
```
```py
root@debian-s-4vcpu-16gb-amd-fra1-01
▶ ~ # apt install openjdk-21-jdk -y
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
E: Unable to locate package openjdk-21-jdk
```
```py
root@debian-s-4vcpu-16gb-amd-fra1-01
▶ ~ # sdk list java
```
```
================================================================================
Available Java Versions for Linux 64bit
================================================================================
 Vendor        | Use | Version      | Dist    | Status     | Identifier
--------------------------------------------------------------------------------
 Corretto      |     | 24.0.1       | amzn    |            | 24.0.1-amzn         
               |     | 24           | amzn    |            | 24-amzn             
               |     | 23.0.2       | amzn    |            | 23.0.2-amzn         
               |     | 21.0.7       | amzn    |            | 21.0.7-amzn         
               |     | 21.0.6       | amzn    |            | 21.0.6-amzn         
               |     | 17.0.15      | amzn    |            | 17.0.15-amzn        
               |     | 17.0.14      | amzn    |            | 17.0.14-amzn        
               |     | 11.0.27      | amzn    |            | 11.0.27-amzn        
               |     | 11.0.26      | amzn    |            | 11.0.26-amzn        
               |     | 8.0.452      | amzn    |            | 8.0.452-amzn        
               |     | 8.0.442      | amzn    |            | 8.0.442-amzn
```               
```py
root@debian-s-4vcpu-16gb-amd-fra1-01
▶ ~ # sdk install java 21.0.7-amzn 

Downloading: java 21.0.7-amzn

In progress...
#########################################################################100.0%
Repackaging Java 21.0.7-amzn...

Done repackaging...

Installing: java 21.0.7-amzn

Done installing!

Setting java 21.0.7-amzn as default.
```