# elgato

Elgato [Key Light Air](https://www.elgato.com/us/en/p/key-light-air) management from Bash

Inspired by [Trevor Sullivan's](https://github.com/pcgeek86) [Elgato PowerShell](https://github.com/pcgeek86/elgato) module.

## Install

```shell
curl -o elgato https://raw.githubusercontent.com/grantcarthew/bash-elgato/main/elgato
chmod +x elgato
sudo mv elgato /usr/local/bin/
elgato -h
```

## Usage

```text
Usage: elgato <command> <ip_address_list> [--help]

Basic Elgato light management for Bash

Command list:
  on                 Turn the light(s) on
  off                Turn the light(s) off

Example:
$ elgato on 172.30.1.181 172.30.1.143

Dependencies:
  curl               The Client for URLs CLI tool

Required arguments:
  command            The light command, see above
  ip_address_list    A space separated list of light IP addresses

Optional arguments:
  -h, --help         Show this help message and exit
```

## API Reference

The Elgato lights have the following REST API once connected to your WiFi.

Determine the IP address of the lights. There is probably a UDP broadcast for finding the lights which is unknown at this point.

REST Endpoint:

- TYPE: http (not encrypted)
- AUTH: None
- PORT: 9123
- PATH: `/elgato/lights`

REST Methods:

- GET: Returns the JSON below with the current state of the light
- POST: With the below JSON payload, sets the state of the light

REST JSON Payload:

```json
{
    "numberOfLights": 1,
    "lights": [
        {
            "on": 1,
            "brightness": 9,
            "temperature": 150
        }
    ]
}
```

Example: See the [curl command](https://github.com/grantcarthew/bash-elgato/blob/ff177a48b64b43c4de40a1d67099ea28ee5682e9/elgato#L143) from the Bash script.