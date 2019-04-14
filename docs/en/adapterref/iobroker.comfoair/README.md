![Logo](admin/comfoair.png)

# ioBroker.comfoair

![Number of Installations](http://iobroker.live/badges/comfoair-installed.svg) ![Number of Installations](http://iobroker.live/badges/comfoair-stable.svg) [![NPM version](http://img.shields.io/npm/v/iobroker.comfoair.svg)](https://www.npmjs.com/package/iobroker.comfoair)
[![Downloads](https://img.shields.io/npm/dm/iobroker.comfoair.svg)](https://www.npmjs.com/package/iobroker.comfoair)

[![NPM](https://nodei.co/npm/iobroker.comfoair.png?downloads=true)](https://nodei.co/npm/iobroker.comfoair/)

An ioBroker adapter for Zehnder Comfoair  'CA' -ventilations (i.e. ComfoAir CA350, NOT ComfoAir Q350...)

To use this adapter, you need a RS232 to LAN oder WiFi Converter to connect ioBroker with your Zehnder Comfoair.
Install hardware for TCP - connection to comfoair: i.e. RS232 to LAN adapter to the serial interface of the comfoair. Connect Pins 2, 3 and 5 only (should work also with TX, RX and GND - contacts of the cc-Ease connection too).
Actually this adapter works only with a LAN-Connection. A direct link based on a direct serial connection is in development.

Install adapter, create instance.

## Config

Set comfoair - IP-adress, port and polling - intervall.

## Adapter & CC Ease

In general it is not recommended to send data form 2 transmitters to one reciever in RS232 serial communication. The parallel use of CCEase and adapter can result in errors or, worst case, in damage to your comfoair-control! Therefore, when you start the ComfoAir - adapter your CC Ease will be shut down.
The comfoair itself knows 4 different rs232-modes: CCEaseonly, PConly, PCMaster, PCLogmode. In PConly and PCMaster, CC-Ease is off.
Once your adapter is running you can choose on of the following (adapter - rs232) modes, switching the control.rs232mode - object.

### CC Ease only

CC Ease is running, but your adapter will niether get data from the comfoair nor send commands! (rs232mode is CCEaseonly)

### Adapter only

CC Ease is shut down, you can control your comfoair only with ioBroker. (rs232mode ist PCMaster, is default & recommended)

### Parallel Mode

CC Ease and adapter are running. comfoiar rs232mode is set to 'PCLogmode'. You can control your ComfoAir with ioBroker and with the CC Ease unit. Tests have shown errorless - running in parallel for a longer period of time. But: You run this mode on your own risk.

## Using the adapter

Values of your comfoair should be visible in the 'status' and the 'temperatures' channel.

By setting/changeing values in the 'control' - channel, you control your comfoair ventilation. All values in the 'control' - channel have to be set wieth ACK=false to be recognized as commands for the adapter.

Tested on comfoair CA350.

## Changelog

### 0.2.1

- smaller bugfixes.

### 0.2.0

-   New rs232 - Modes, reading enthalpie-values, handling connection-errors.

### 0.1.4

-   README-Update 'NO PARALLEL USE', discard 'Safe-Mode'.

### 0.1.3

-   RS - 232 interface: manual- or safe - mode possible.

### 0.1.2

-   ReadME updated, minor bugfixes.

### 0.1.1

-   bugfix ventlevels, reading errors

### 0.1.0

-   ReadME Update

### 0.0.7

-   Core Files/Testing Update and introduce adapter-core

### 0.0.6

-   Filter - change - indicator.

### 0.0.5

-   bugfig set vent levels.

### 0.0.4

-   gets & sets vent levels, gets filter-timer.

### 0.0.3

-   minor bugfixes, sets comfort-temperature and resets filter-hours.

### 0.0.2

-   First running Version. Gets temp, vent, bypass and filter states, sets fan level.

### 0.0.1

-   In development stage, contributions welcome

## License

The MIT License (MIT)

Copyright (c) 2019 forelleblau marceladam@gmx.ch

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.