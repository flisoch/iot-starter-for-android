# IoT Starter for Android
IoT Starter is a demo application for interacting with IBM Watson IoT Platform. This fork provides and opportunity to connect to ThingsBoard IoT Platform instead of IBM Watson IoT Platform.
The application turns your mobile device into a sensor that publishes and receives data to and from the cloud using the MQTT protocol.


This application demonstrates using an Android device as one an IoT device, and provides a variety of events and commands that it can publish or receive data to and from.
The application from this fork can publish Accelerometer data and receive Color command only. Touchmove, Text, Light, Alert events and commands are not supported. 



## How it works
A device that is registered with ThingsBoard IoT Platform may publish and subscribe to data that is presented as either an event or command using the MQTT protocol.
The Eclipse Paho MQTT Android Service is used to publish and subscribe to ThingsBoard IoT Platform. This can be downloaded from
[Eclipse Paho MQTT Android Service](http://www.eclipse.org/paho/clients/android/).

MQTT is a lightweight messaging protocol that supports publish/subscribe messaging. With MQTT, an application publishes messages to a topic. These messages may then be received by another application that is subscribed to that topic. This allows for a detached messaging network where the subscribers and publishers do not need to be aware of each other.
The topics used by this application can be seen in the table below:

## Topics
|Topic|Sample Topic|Sample Messages|
|:---------- |:---------- |:------------|
|`v1/devices/me/rpc/request/$resuestId`|`v1/devices/me/rpc/request/12345`|`{"method":"getColorsFromAccel","params":{"acceleration_x":-2.5065534,"acceleration_y":2.5568595,"acceleration_z":11.147109,"roll":0.22118242,"pitch":-0.22015898,"yaw":-0.30368638,"longitude":0.0,"latitude":0.0,"heading":0.0,"speed":0.0,"trip_id":"1637218763","timestamp":"2021-11-18T09:59:43.716+03:00"}}`|

For more information on the MQTT protocol, see http://mqtt.org/.

## Try it

### Connect to an IoT organization as a registered device
In order to try the application as a registered device, you must have a Samsung IT Academy account and ThingsBoard Tenant Administrator account or have ThingsBoard installed locally. 

On launching the application for the first time, you will need to enter your credentials to connect your device to ThingsBoard IoT Platform. The required information to connect your device includes:

- Hostname or ip address of ThingsBoard server (Samsung IT Academy server ip by default)
- Your device username. This is returned when registering your device with ThingsBoard IoT Platform. This can be authorization token if your device credential type is Access Token. Or this can be username if your device credential type is MQTT Basic.
- Your device password. This is returned when registering your device with ThingsBoard IoT Platform. If you didn't set password while managing your device, the password can be any string. 

Once you have entered the necessary credentials, you may activate your device as a sensor. Pressing the 'Activate Sensor' button will connect the device to ThingsBoard IoT Platform and allow it to begin publishing and receiving data.

## Prerequisites
Required:
- A [ThingsBoard](https://thingsboard.io/) platform installed and running locally or student account for connection to ThingsBoard hosted on Samsung IT Academy server. 
- An Android SDK installation

## Installation
1. `git clone https://github.com/flisoch/iot-starter-for-android.git`
2. Launch Android Studio and select "Open an Existing Android Studio Project".
3. Navigate to your `iot-starter-for-android` folder and open the project.
4. Run the application.

## Notes
In order to really see this demo do something, you must have an application to consume its data and publish data back
to the IoT Starter application. RuleChain has to be configured on ThingsBoard platform so that it receives rpc mqtt requests and replies to them.


## Resources
- [IoT Starter for iOS](https://github.com/ibm-messaging/iot-starter-for-ios)
- [ThingsBoard](https://thingsboard.io/)
- [MQTT](http://mqtt.org/)
