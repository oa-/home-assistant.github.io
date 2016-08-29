---
layout: page
title: "Bluetooth LE Tracker"
description: "Instructions for integrating bluetooth low-energy tracking within Home Assistant."
date: 2016-08-24 00:00
sidebar: true
comments: false
sharing: true
footer: true
logo: bluetooth.png
ha_category: Presence Detection
ha_iot_class: "Local Poll"
ha_release: 0.27
---

This tracker discovers new devices on boot and in regular intervals and tracks bluetooth low-energy devices periodically based on interval_seconds value. It is not required to pair the devices with each other! 
Devices discovered are stored with 'BLE_' as the prefix for device mac addresses in `known_devices.yaml`.

<p class='note'>
Requires PyBluez. If you are on Raspbian, make sure you first install `bluetooth` and `libbluetooth-dev` by running `sudo apt install bluetooth libbluetooth-dev`
</p>

To use the Bluetooth tracker in your installation, add the following to your `configuration.yaml` file:

```yaml
device_tracker:
  platform: bluetooth_le_tracker
```

As some BT LE devices change their MAC address regularly, a new device is only discovered when it has been seen 5 times.
Some BTLE devices (e.g. fitness trackers) are only visible to the devices that they are paired with. In this case, the BTLE tracker won't see this device.

BTLE tracking requires root privileges.

For additional configuration variables check the [Device tracker page](/components/device_tracker/).
