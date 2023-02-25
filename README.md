# osx-kvm-stuff

This is a personal repo that is designed to make it easier to work with [OSX-KVM](https://github.com/kholia/OSX-KVM). It also makes use of [an amazing hack](https://github.com/sickcodes/Docker-OSX#usbfluxd-iphone-usb---network-style-passthrough-osx-kvm-docker-osx) that allows you to passthrough USB over the network* so you can run XCode on an iPhone without needing to buy a Mac.

*If you can passthrough a USB host, that will be much easier. I don't have enough USB ports for that :(


## Instructions

To use the OSX-KVM stuff, go to the first repo linked above to install OSX-KVM. You may not want my config or helper scripts, but if you do, then check out the `OSX-KVM-stuff` folder.

To use the USB-over-network stuff, check the second repo linked above, and check out the `usb-passthrough` folder in this repo for the startup scripts I use to get that working.


## HOWTO

- Share a folder between the host and the client:
  - In the host:
    - Install Webmin
    - Set up a Samba share:
      - Allow full permissions
      - Add custom options:
        - guest ok = yes
        - create mask = 0644
        - directory mask = 0755
    - Restart the Samba service:
      - `sudo systemctl restart smbd`
  - In the VM:
    - Setup a one-time connection to a remote server:
      - Finder -> Go -> Connect to Server:
        - Enter the URL of the host or share (e.g. `smb://192.168.1.100/` or `smb://192.168.1.100/your_share_name`)
        - Connect as guest
      - The share should now be available at `/Volumes/your_share_name`
    - Mount the remote share automatically on boot:
      - Set up the share using the instructions in the above section
      - System Preferences -> Users and Groups -> Select User -> 'Login Items' tab
        - Select the mounted share
