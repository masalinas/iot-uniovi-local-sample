# Description

IoT MQTT Local Sample

## Install MQTT message broker service

We are using a nodeJS MQTT broker implementation by [Aedes](https://github.com/moscajs/aedes) a evolution of [Mosca](https://github.com/moscajs/moscamosca)

To start MQTT Broker service execute these commands:

```shellAed
cd broker
npm install
node .
```

## Install node-RED service

To start node-RED service execute these commands:

```shell
cd node-red
npm install
npm runn start
```

If we want secure our node-RED service we must install node-red-admin package

```shell
npm install -g --unsafe-perm node-red-admin
```

Excute this command generate a new password hashed and configure the settings correctly

```shell
node-red-admin hash-pw
```

## Test Broker from shell

To test the broker form shell we could use the MQTT clients **mqtt_sub** and **mqtt_pub** shell clients.

To subscribe to a topic called 'test' in localhost

```shell
mqtt_sub -h localhost -t test
```

To published a message to a topic 'test' in localhost qith QoS 1

```shell
mqtt_pub -h localhost -t test -q 1 -m 'Hello IoT from shell'
```