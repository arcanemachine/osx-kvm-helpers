# usb-passthrough

This section made possible by [this repo](https://github.com/sickcodes/Docker-OSX#usbfluxd-iphone-usb---network-style-passthrough-osx-kvm-docker-osx).

These scripts are used to easily enable USB-over-network passthrough for a macOS VM instance.

Instructions: Run the start scripts in order: `start-host-1-docker-over-usb`, `start-host-2-docker-over-usb`, `start-host-3-docker-over-usb`. Let them run (if they want to) until you are finished with the VM.

In the macOS VM, run the script `start-client-1-docker-over-usb`. The dependencies (listed in the script) should be installed before running the script.

~~To get this working, I always need to run these scripts *before* starting the VM. Sometimes, it doesn't work the first time and a VM restart is required.~~ (I no longer have this issue.)

Good luck!


## Troubleshooting

- The scripts run but the device doesn't show up in Xcode
  - Ensure that the underlying `systemd` services are working:
    - e.g. `sudo systemctl status usbmuxd.service`

- The device shows up but sometimes disappears.
  - Try the action or command again. Sometimes the device is not detected on the first try.
  - Try stopping and starting the `docker-over-usb` client script and see if that fixes it.
  - If in doubt, the device usually shows up in Xcode.

- The device is connected but not detected by the Flutter runner
  - Connect the device via Xcode and try the build again.
