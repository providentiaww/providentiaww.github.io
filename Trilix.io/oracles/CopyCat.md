# CopyCat Oracle

This application is a simple JSON echo tool designed to be used for Blockchain Oracle use and as an initial integration point with the Trilix platform.

The oracle uses MQTT for communications. Connection details are available in the testing section.

## Testing

Basic testing setup outlined below.

| Setting | Value |
| -- | -- |
| user | mqttguest |
| password | Aej7Gei{Quae_w6aUSh^aCh9 |
| host | mqtt-dev.maa.trilix.io |
| standard port | 1883 |
| ~~TLS port~~ | ~~8883~~ \* |
| submit topic | mqtt/event/copycat/req |
| reply topic | mqtt/event/copycat/resp |
| submit format | JSON |
| response format | JSON |

Provide any JSON input to the submit topic and a reply will be generated with your source data and some additional fields added to demonstrate capability of the CopyCat oracle.

### Testing Demo
There is a test driver `mqtt-driver.py`. It uses public APIs to grab new JSON input data and submits to the topic as per above.
```
(mqtt) rquick@build02:~/src/4dbc/oracle/copycat/tests$ ./mqtt-driver.py --help
usage: mqtt-driver.py [-h] [-b] [-s] [-d] [-a API]

options:
  -h, --help         show this help message and exit
  -b, --blast        Send quick messages derived from API. (Default Behavior)
  -s, --slow         Run continuous slow posts
  -d, --debug        Debug messages
  -a API, --api API  API: ['cryptoNews', 'indiaNews', 'covidData']
```

We also support the [MQTT Cool](https://testclient-cloud.mqtt.cool) testing client with the configuration as designated above. This is a *shared connection*.

---
\* TLS is not yet available. Check back here for updates and for the processes to get client certificates for testing.