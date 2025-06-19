# Multisensor-Device
Frugal device w/multiple sensors can communicate via http, mqtt, and espNow for local or remote monitoring of temperature, humidity, moisture, motion, illumination, door/window status, and asset disturbance

## Hardware
The device takes advantage of the Expressif ESP32 microcontroller prototype board, which can be programmed in C++ using the Arduino IDE as well as other IDE's.  Its built-in WiFi antenna enables wireless communication with or without access to a router.

## Software

### Operating Modes
The software can be configured for one of four modes, depending one the awakeTime and sleepTime settings.  Modes 1 thru 3 involve being awakened from a deep sleep state by a timer or an interrupt (a door opening or motion occuring).  The fourth mode is one where the processor never sleeps, but instead continuously polls the sensors:
  
  - Mode 1 - The processor is awakened by an interrupt. It measures and reports on the interrupt and goes back to sleep.

  - Mode 2 - The processor is awakened by and interrupt or timer. It records the sensors, reports on them, interrupt and goes back to sleep.

  - Mode 3 - The processor is awakened by and interrupt or timer. It records the sensors, and then waits a fixed time to receive data requests from clients.  After a fixed time, it goes back to sleep.

  - Mode 4 - The processor neveer sleeps. polls the sensors and reports on them or waits for a data request.

### Communication Capabilities

  - ESPNOW with another ESP32 which is acting as a central data collector (or perhaps reports via cellular modem, etc.).
    
  - http server wireless connection without a router.
    
  - WiFi router, giving access to the many ioT tools available on the internet.
    
  - MQTT protocol to communicate with Home Assistant or others.
 
