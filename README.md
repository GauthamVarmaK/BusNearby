# BusNearby
A project to alert when bus is nearby or at the stop.

Follow the [link to Check it Out in Action](https://www.youtube.com/watch?v=gG0qXoqHh5M)


## About the Project:

At every stop on an average, we waste about 2 min on an average, but around 30 stops over one ride means about 1 hour.  So by this project, the time bus has to stay at the stop goes down to 45 sec, which means about 1 min 15 sec is saved per stop or about 37.5 minutes per ride is saved. The project helps in energy saving by drastically reducing bus waiting period at stops, during which the engine still keeps running consuming power. This leads to saving fuel, energy, and human time and avoids traffic congestion with office traffic and helps reduce air pollution.

## Physics behind the rgb bulb:

LED are an efficient way of lightning. Different colour channels are controlled by different channels, individually by Pulse width modulation to result in varying Duty cycles for each colour, generating the colours on the RGB Bulb. Hence converting the electricity to light energy of the desired wavelength.

## Technical Working:

In this setup, I have a server (I used an inexpensive raspberry Pi), smart bulb and a connected phone. The bus continuously pings for the location of the bus every 30 seconds (via a custom API which extracts the bus coordinates from the bus tracking web page via http requests) and then checks if the bus entered a geofence zone such as if the bus is nearby or at the bus stop. As the bus enters the geofenced location the server will trigger an action which will make an MQTT message to the bulb topic. The bulb has been flashed with a custom firmware called Tasmota. Hence it supports for local MQTT messages. As the bus is subscribed to the MQTT topic, turn on and set the colour as per message published on the MQTT server. Also, the server will send a push notification to the connected mobile via an application. This will ensure seamless functionality while retaining low resource consumption.

## Resources, software, and protocols used:

- Python
- NodeJS
- Tasmota
- Http
- TLS
- MQTT
- Android studio
- Etc.
