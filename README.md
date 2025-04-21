# DigitalOcean - PaperMC


![DigitalOcean](https://img.shields.io/badge/DigitalOcean-%230167ff.svg?style=for-the-badge&logo=digitalOcean&logoColor=white) ![Debian](https://img.shields.io/badge/Debian-D70A53?style=for-the-badge&logo=debian&logoColor=white)

A repository containing the configuration files for my Minecraft server.  

```yml
root@debian-s-4vcpu-16gb-amd-fra1-01
▶ ~ # neofetch
       _,met$$$$$gg.          root@debian-s-4vcpu-16gb-amd-fra1-01 
    ,g$$$$$$$$$$$$$$$P.       ------------------------------------ 
  ,g$$P"     """Y$$.".        OS: Debian GNU/Linux 12 (bookworm) x86_64 
 ,$$P'              `$$$.     Host: Droplet 20171212 
',$$P       ,ggs.     `$$b:   Kernel: 6.1.0-33-amd64 
`d$$'     ,$P"'   .    $$$    Uptime: 2 days, 1 hour, 17 mins 
 $$P      d$'     ,    $$P    Packages: 1102 (dpkg) 
 $$:      $$.   -    ,d$$'    Shell: bash 5.2.15 
 $$;      Y$b._   _,d$P'      Resolution: 1024x768 
 Y$$.    `.`"Y$$$$P"'         Terminal: /dev/pts/0 
 `$$b      "-.__              CPU: DO-Premium-AMD (4) @ 2.299GHz 
  `Y$$                        GPU: 00:02.0 Red Hat, Inc. Virtio 1.0 GPU 
   `Y$$.                      Memory: 282MiB / 15992MiB 
     `$$b.
       `Y$$b.                                         
          `"Y$b._                                     
              `"""


root@debian-s-4vcpu-16gb-amd-fra1-01
▶ ~ # 
```
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

## Description

Configuration files for my Minecraft PaperMC 1.21.4 server hosted on DigitalOcean. This setup includes essential plugins for server management, world editing, permissions, player list display, and multi-world support.

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
