# osx-kvm-stuff

This is a personal repo that is designed to make it easier to work with [OSX-KVM](https://github.com/kholia/OSX-KVM). It also makes use of [an amazing hack](https://github.com/sickcodes/Docker-OSX#usbfluxd-iphone-usb---network-style-passthrough-osx-kvm-docker-osx) that allows you to passthrough USB over the network* so you can run XCode on an iPhone without needing to buy a Mac.

*If you can passthrough a USB host, that will be much easier. I don't have enough USB ports for that :(

# Instructions

To use the OSX-KVM stuff, go to the first repo linked above to install OSX-KVM. You probably don't want my config or helper scripts, but if you do, then check out the `OSX-KVM-stuff` folder.

To use the USB-over-network stuff, check the second repo linked above, and check out the `usb-passthrough` folder to see the possibly-useful scripts to get that working.
