# Mosquitto Docker container

Running the [Mosquitto message broker](https://mosquitto.org/) in a Docker container based on the lightweight [Alpine Linux](https://alpinelinux.org/) OS.

> Eclipse Mosquitto™ is an open source (EPL/EDL licensed) message broker that implements the MQTT protocol versions 3.1 and 3.1.1. MQTT provides a lightweight method of carrying out messaging using a publish/subscribe model. This makes it suitable for "Internet of Things" messaging such as with low power sensors or mobile devices such as phones, embedded computers or microcontrollers like the Arduino.

Works great with [Home Assistant to handle MQTT](https://home-assistant.io/components/mqtt/).
Also includes the client packages to publish & subscribe using the CLI.

## Usage

Start the message broker

    docker run -p 1883:1883 --name mosquitto trafex/alpine-mosquitto
    
Use the client to subscribe on a topic
    
    docker exec -ti mosquitto mosquitto_sub -h 127.0.0.1 -v -t '#'
    
Use the client to publish to a topic
    
    docker exec -ti mosquitto mosquitto_pub -h 127.0.0.1  -t 'hello' -m 'world'

