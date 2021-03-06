# Nettigo Air Monitor Firmware

NAMF is a firmware for [Nettigo Air Monitor Sensor](https://nettigo.eu/products/tagged/NAM) - a modular platform for measuring air quality. Hardware is OSHWA Certified with [UID PL000001](https://certification.oshwa.org/pl000001.html).

NAM Sensor features WiFi connectivity provided by ESP8266 (and ESP32 in future). It's build around Nova Fitness SDS011 PM sensor. Device has a build-in PTC heater with control circuitry for air conditioning in a high humidity environment (to avoid counting water vapor as dust).

### Changelog

The code base has roots in [Luftdaten.info firmware](https://github.com/opendata-stuttgart/sensors-software/). We aim to rewrite the code to make it modular, easier to modify and extend in future. 

Detailed changelog is in [Versions](Versions.md).

### Firmware web interface

* / - main menu
* Data related:
  * /values - current measured values and basic debug information
  * /data.json - measured values in JSON format
  * /metrics - measured values in Prometheus format
* Configuration related:
  * /config - configuration
  * /removeConfig - remove configuration files
  * /config.json - current configure file in JSON format
  * /configSave.json - form for pasting configuration file
  * /forceUpdate - form for changing update server or link to other binary file
  * /wifi - list of wifi networks (active only in AP mode)
* /reset - sensor reboot
* /debug?lvl=x - sets debug serial messages info level to x:
  * 0 - no debug
  * 1 - errors
  * 2 - errors & warnings
  * 3 - errors, warnings & min. info
  * 4 - errors, warnings, min. info & med. info
  * 5 - all debug messages
* /images - serving images - used for the NAM logo