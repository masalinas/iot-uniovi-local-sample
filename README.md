# Description

IoT local samples from MQTT and node-RED services

## Install MQTT message broker service

We are using a nodeJS MQTT broker implementation by [Aedes](https://github.com/moscajs/aedes) a evolution of [Mosca](https://github.com/moscajs/moscamosca)

To start MQTT Broker service execute these commands:

```shellAed
cd broker
npm install
node .
```

## Test MQTT message broker service from shell

To test the broker form shell we could use the MQTT clients **mqtt_sub** and **mqtt_pub** shell clients. To install these clients executed this command from shell:

```shell
sudo apt-get install mosquitto-clients
```

To subscribe to a topic called 'test' in localhost

```shell
mqtt_sub -h localhost -t test
```

To published a message to a topic 'test' in localhost qith QoS 1

```shell
mqtt_pub -h localhost -t test -q 1 -m 'Hello IoT from shell'
```

## Install node-RED service

To start node-RED service execute these commands:

```shell
cd node-red
npm install
npm run start
```

If we want **securize** our node-RED service we must install node-red-admin package previously to creare a default admin password.

```shell
npm install -g --unsafe-perm node-red-admin
```

Excute this command to generate a new node-RED password hashed and configure the settings correctly:

```shell
node-red-admin hash-pw
```

The default password configured it's **admin/password**
