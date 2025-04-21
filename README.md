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

## Java 21 installation

Initially, I encountered an issue where `apt` would not install Java 21 — required by newer versions of PaperMC. It only had Java 17 available in the default Debian 12 repositories.

### Problem
```bash
root@debian-s-4vcpu-16gb-amd-fra1-01
▶ ~ # apt install openjdk-21-jdk-headless
E: Unable to locate package openjdk-21-jdk-headless

root@debian-s-4vcpu-16gb-amd-fra1-01
▶ ~ # apt install openjdk-21-jdk
E: Unable to locate package openjdk-21-jdk
```

### Solution: Installing Java 21 (Amazon Corretto) with SDKMAN!

I solved the issue by installing [SDKMAN!](https://sdkman.io/) and using it to install Java 21 (Amazon Corretto) **both for the root user and for the `mc` user who runs the Minecraft server**.

#### 1. Install SDKMAN:
```bash
curl -s "https://get.sdkman.io" | bash
source "$HOME/.sdkman/bin/sdkman-init.sh"
```

#### 2. Install Java 21 (Amazon Corretto):
```sh
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
```bash
sdk install java 21.0.7-amzn
```
#### 3. Confirm installation:
```bash
java -version
# Output should be something like:
openjdk version "21.0.7" 2025-04-15 LTS
OpenJDK Runtime Environment Corretto-21.0.7.6.1 (build 21.0.7+6-LTS)
OpenJDK 64-Bit Server VM Corretto-21.0.7.6.1 (build 21.0.7+6-LTS, mixed mode, sharing)
```

This allowed me to successfully launch PaperMC 1.21.4 with full Java 21 support.
