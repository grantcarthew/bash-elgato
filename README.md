# elgato

Elgato [Key Light Air](https://www.elgato.com/us/en/p/key-light-air) management from Bash

Inspired by [Trevor Sullivan's](https://github.com/pcgeek86) [Elgato PowerShell](https://github.com/pcgeek86/elgato) module.

## Install

```shell
curl -o elgato https://raw.githubusercontent.com/grantcarthew/bash-elgato/main/elgato
chmod +x elgato
mv elgato /usr/local/bin/
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

Optional arguments:
  -h, --help         Show this help message and exit
```