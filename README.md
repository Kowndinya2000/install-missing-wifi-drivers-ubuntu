# install-missing-wifi-drivers-ubuntu (18.04 LTS)
1. Understood that the wifi drivers are from Intel Corporation (try any of these commands below)
``` 
lspci -v | grep Wireless
sudo lspci -nn | grep -i network
sudo lspci -nn -d 14e4
sudo lspci -nn -d 14e4:
sudo lspci -nn -d 14e4:
```
2. Clone the GitHub repo containing files for the linux-firmware at [here](https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git)
```
git clone https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git
```
3. Copy these files to your machine from the downloaded repo
```
sudo cp iwlwifi-*.{ucode,pnvm} /lib/firmware
```
4. Created a bootable usb device by downloading 18.04 iso and flashing it to a usb.
5. Copied the dkms.deb file to this machine and installed dkms 
```
tree -afi | grep .deb
copy the required dkms.deb file
```
6. Download and install the backport-iwlwifi-dkms.deb file from here
```
http://archive.ubuntu.com/ubuntu/pool/universe/b/backport-iwlwifi-dkms/
```
7. Reboot the machine
```
sudo reboot
```
