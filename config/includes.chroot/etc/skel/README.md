This installation installs apt sources.list entries to  repositories that are not part of the LinuxCNC project but are complementary to it.
They are provided as a convenience to users but there is no guarantee they will work. 
No software is installed by this installer from these repositories.
Before attempting to install additional packages be sure to:
sudo apt update
sudo apt upgrade

To upgrade tto the latest linuxCNC packages the following commands will retrieve the latest version of LinuxCNC V 2.9 from the buildbot
sudo apt update
sudo apt upgrade

These repositories include:
QTYPYVCP - an alternative framework for building GUI's for linuxcnc.
To install qtpyvcp and available GUI's: 
  sudo sudo apt install python3-qtpyvcp
  sudo apt install python3-probe-basic
  sudo apt install python3-monokrom
  sudo apt install python3-turbonc

Ethercat which requires the folloing packages
ethercat-master - popular open source ethercat master from IgH Etherlab https://gitlab.com/etherlab.org/ethercat
lib-ethercat - devlopment interface to ethercat-master
linuxcnc-ethercat - driver for LinuxCNC 

All of these need installing to use ethercat hardware from linuxCNC. This can be done as follows:
  sudo apt install ethercat-master libethercat-dev  linuxcnc-ethercat
Additional steps are required to complete an ethercat instalation. 
Currently these are described ion the linuxCNC forum here
https://forum.linuxcnc.org/ethercat/45336-ethercat-installation-from-repositories-how-to-step-by-step

Note that lib-ethercat and some network drivers require use of dkms. Because dkms modifies the kernel, 
this is not permitted on UEFI/secure boot systems unless dkms is enrolled in the UEFI system.
This is beyond the scope of this document.

For further informatin about configuring Debian 12 (Bookworm), refer to the Getting Linuxcnc chapter in the 2.9 Documents

