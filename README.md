bluetooth-lock
==============

Lock/unlock computer based on proximity of bluetooth device (e.g. your phone or tablet).

This works for me under Ubuntu 13.04 with Gnome desktop. YMMV.

- First step is to pair your device with your computer
- Then run `bluez-test-device list` to get the device address
- Then configure the script to run in the background at system startup

Here's how it works: the script pings the bluetooth device every 60 seconds (by default).
When the device moves out of range of the computer, the pings fail and the screen will lock.
Once the device is out of range, the script pings every second attempting to find the device again. As
soon as it pings successfully (you're back in range) the screen will automatically unlock again.

This replicates the basic functionality of [blueproximity](https://launchpad.net/blueproximity) which
I couldn't get to work reliably. You might have better luck with that package.
