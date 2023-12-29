# Homebridge

## SETUP MQTT
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
