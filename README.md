# Homebridge

## SETUP MQTT
*ref: [video](https://youtu.be/efmsed9Aj-o?si=00LuOsp-vYOo1eDA)*
### INSTALL
#### MQTT
Run the following command:
``` sh
curl -sk https://raw.githubusercontent.com/DeamonCorpse/Homebridge/main/MQTT%20Install | sudo bash -
```

#### Zigbee2MQTT
Run the following command:
```sh
curl -sk https://raw.githubusercontent.com/DeamonCorpse/Homebridge/main/Zigbee2MQTT%20Install | sudo bash -
```

> **IMPORTANT**
> After the Zigbee2MQTT install completes, the system will reboot.
> BEFORE running `npm start`, you must 1st stop the mqtt service with `sudo systemctl stop zigbee2mqtt`
> THEN run `npm start`

#### Troubleshooting
If you get [Resource temporarily unavailable Cannot lock port](https://www.zigbee2mqtt.io/guide/installation/20_zigbee2mqtt-fails-to-start.html#error-resource-temporarily-unavailable-cannot-lock-port):

1 - Ensure the user running Zigbee2MQTT has write access to the port:
```sh
test -w /dev/ttyUSB0 && echo success || echo failure
```
if `failure`:
``` sh
sudo chown pi /dev/ttyUSB0
```
For more information, see [Verify that the user you run Zigbee2MQTT as has write access to the port](https://www.zigbee2mqtt.io/guide/installation/20_zigbee2mqtt-fails-to-start.html#verify-that-the-user-you-run-zigbee2mqtt-as-has-write-access-to-the-port).

2 - Find and kill all the processes using the port:
``` sh
sudo fuser -k /dev/ttyUSB0
```

### TIPS & TRICKS
Check this [video](https://youtu.be/wgbCjs0yH4M?si=GkhC-g6RNbxEYoez)

### UPDATE
*ref: [Update Zigbee2MQTT to the latest version](https://www.zigbee2mqtt.io/guide/installation/01_linux.html#for-later-update-zigbee2mqtt-to-the-latest-version)*

Run the following command:
``` sh
cd /opt/zigbee2mqtt
./update.sh
```
