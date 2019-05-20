# Home Assistant Docker

## Description

This is a version of Home Assistant with a MQTT server running inside a Docker container.

## How to run it on your machine

### Home Assistant configuration

- run `docker-compose up`
- run `hostname -I` in Linux shell of the host machine and take the first IP address you get
    - in this case that would be `192.168.0.17`
- inside Home Assistant web UI go to `Configuration` -> `Integrations` -> `ADD` (+ button on the bottom right) -> `MQTT`
- in field broker put `192.168.0.17` and set the port to `1883`
    - if you set username and password in your MQTT server, fill them in too
- in HA's `configuration.yaml` put 
```
mqtt:
   broker: "192.168.0.17"
```
- run `docker-compose reset`

### MQTT client configuration

- connect the client to the same WiFi as the host machine
- put `192.168.0.17` as broker IP

## Usage

Once you have your Home Assistant (and MQTT) set up, visit `192.168.0.17:8123` from any browser on the same local network and control your devices!