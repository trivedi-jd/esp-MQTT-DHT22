# ESP32 MQTT DHT22  

This projects connects to the broker URI selected using `idf.py menuconfig` (using mqtt tcp transport), reads temperature and humidity data from DHT22 sensor and publishes the data in JSON format to the MQTT topic `temp-humidity/mqtt/esp32/publish`.

It uses ESP-MQTT library which implements mqtt client to connect to mqtt broker.

## Project References

### MQTT Application Reference

This project is based on the ESP-IDF v 5.2.2 [ESP-MQTT sample application](https://github.com/espressif/esp-idf/tree/master/examples/protocols/mqtt/tcp)

### DHT22 Sensor Reference
For interfacing the DHT22 sensor this projects has taken the code from as is from
- [DHT22](https://github.com/gosouth/DHT22)
- [DHT22-lib-for-esp-idf](https://github.com/Andrey-m/DHT22-lib-for-esp-idf)

> [!NOTE]  
> "I Don't Own The Rights” or "No Infringement Intended".

## How to use this Project

### Hardware Required
This example can be executed on any ESP32 board.

- ESP32 Board.
- DHT22 Sensor Module.
- WiFi and connection to internet.


### Configure the project

* Open the project configuration menu (`idf.py menuconfig`)
* Configure Wi-Fi or Ethernet under "Example Connection Configuration" menu.

### Build and Flash

Build the project and flash it to the board, then run monitor tool to view serial output:

```
idf.py -p PORT flash monitor
```

(To exit the serial monitor, type ``Ctrl-]``.)

See the Getting Started Guide for full steps to configure and use ESP-IDF to build projects.

## Example Output

```
I (4783) esp_netif_handlers: example_netif_sta ip: 192.168.1.8, mask: 255.255.255.0, gw: 192.168.1.1
I (4783) example_connect: Got IPv4 event: Interface "example_netif_sta" address: 192.168.1.8
I (5613) example_connect: Got IPv6 event: Interface "example_netif_sta" address: fe80:0000:0000:0000:a6cf:12ff:fe88:4f2c, type: ESP_IP6_ADDR_IS_LINK_LOCAL
I (5613) example_common: Connected to example_netif_sta
I (5623) example_common: - IPv4 address: 192.168.1.8,
I (5623) example_common: - IPv6 address: fe80:0000:0000:0000:a6cf:12ff:fe88:4f2c, type: ESP_IP6_ADDR_IS_LINK_LOCAL
I (5643) mqtt_DHT: Other event id:7
I (5643) mqtt_DHT: Starting DHT Task


I (5643) mqtt_DHT: === Reading DHT ===

E (5653) DHT: Sensor Timeout

I (5653) main_task: Returned from app_main()
I (6423) mqtt_DHT: MQTT_EVENT_CONNECTED
I (6433) mqtt_DHT: sent publish successful, msg_id=0, msg={temp:0.0, humidity:0.0}

I (8433) mqtt_DHT: === Reading DHT ===

I (130733) mqtt_DHT: sent publish successful, msg_id=0, msg={temp:32.3, humidity:75.4}

I (132733) mqtt_DHT: === Reading DHT ===

E (132733) DHT: Sensor Timeout

I (132743) mqtt_DHT: sent publish successful, msg_id=0, msg={temp:32.3, humidity:75.4}

I (134743) mqtt_DHT: === Reading DHT ===

I (134753) mqtt_DHT: sent publish successful, msg_id=0, msg={temp:32.1, humidity:76.0}

I (136753) mqtt_DHT: === Reading DHT ===

E (136753) DHT: Sensor Timeout

I (136753) mqtt_DHT: sent publish successful, msg_id=0, msg={temp:32.1, humidity:76.0}

I (138763) mqtt_DHT: === Reading DHT ===

I (138773) mqtt_DHT: sent publish successful, msg_id=0, msg={temp:32.1, humidity:76.1}

I (140773) mqtt_DHT: === Reading DHT ===

I (140783) mqtt_DHT: sent publish successful, msg_id=0, msg={temp:32.1, humidity:76.1}

I (142783) mqtt_DHT: === Reading DHT ===

I (142793) mqtt_DHT: sent publish successful, msg_id=0, msg={temp:32.1, humidity:76.1}
```
