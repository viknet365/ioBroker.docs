---
BADGE-Number of Installations: http://iobroker.live/badges/zigbee-stable.svg
BADGE-NPM version: http://img.shields.io/npm/v/iobroker.zigbee.svg
BADGE-Downloads: https://img.shields.io/npm/dm/iobroker.zigbee.svg
BADGE-Tests: https://travis-ci.org/ioBroker/ioBroker.zigbee.svg?branch=master
BADGE-NPM: https://nodei.co/npm/iobroker.zigbee.png?downloads=true
---
# Драйвер ioBroker для работы с Zigbee-устройствами
При помощи координатора Zigbee-сети на базе Texas Instruments SoC cc253x (и другими) создается собственная сеть, в которую подключаются zigbee-устройства. Взаимодействуя напрямую с координатором сети, драйвер позволяет управлять устройствами без дополнительных шлюзов/бриджей от производителей устройств (Xiaomi/TRADFRI/Hue). Про устройство Zigbee-сети можно прочитать [тут (на английском языке)](https://github.com/Koenkk/zigbee2mqtt/wiki/ZigBee-network). 

## Оборудование
Для работы необходимо одно из перечисленных устройств, прошитое специальной ZNP-прошивкой: [cc2531, cc2530, cc2530+RF](https://github.com/Koenkk/zigbee2mqtt/wiki/Supported-sniffer-devices#zigbee-coordinator)

![](img/CC2531.png)
![](img/sku_429478_2.png)
![](img/sku_429601_2.png)
![](img/CC2591.png)
Необходимое для прошивки оборудование и процесс подготовки устройства описан [тут (на английском языке)](https://github.com/Koenkk/zigbee2mqtt/wiki/Getting-started) или [тут (на русском языке)](https://github.com/kirovilya/ioBroker.zigbee/wiki/%D0%9F%D1%80%D0%BE%D1%88%D0%B8%D0%B2%D0%BA%D0%B0) 

Подключенные к Zigbee-сети устройства сообщают координатору своё состояние и информируют о событиях (нажатия кнопки, обнаружение движения, изменение температуры). Эти сведения отражаются в виде объектов-состояний ioBroker. Некоторые состояния имеют обратную связь и могут отправлять команды zigbee-устройству при изменении состояния (переключение состояния розетки и лампы, изменение сцены или яркости лампы).

## Работа с драйвером
Для запуска драйвера необходимо указать имя порта, на котором подключено устройство cc253x.
Как узнать порт написано [тут (на русском языке)](https://github.com/kirovilya/ioBroker.zigbee/wiki#%D0%9D%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B0%D0%B4%D0%B0%D0%BF%D1%82%D0%B5%D1%80%D0%B0)

Для подключения устройств необходимо перевести координатор Zigbee-сети в режим сопряжения, нажав зеленую кнопку. Начнется обратный отсчет времени (60 сек) пока будет доступна возможность подключения устройств.
Для подключения Zigbee-устройств в большинстве случаев достаточно нажать кнопку сопряжения на самом устройстве. Но существуют особенности для некоторых устройств. Подробнее о сопряжении с устройствами читайте [тут (на английском языке)](https://github.com/Koenkk/zigbee2mqtt/wiki/Pairing-devices) или [тут (на русском языке)](https://github.com/kirovilya/ioBroker.zigbee/wiki#%D0%9F%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%B8%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%81%D1%82%D0%B2%D0%B0).

После успешного сопряжения, устройство появится в панели устройств. Если устройство появилось в панели устройств, но имеет тип undefined, то это неизвестное устройство и с ним нельзя будет взаимодействовать. Если устройство есть в списке доступных устройств, но добавилось как undefined, то попробуйте удалить устройство и добавить заново.
Если не получается подключить устройство, то напиши issue.

## Дополнительные сведения
Существует [дружественный проект](https://github.com/koenkk/zigbee2mqtt) со схожим функционалом на тех же технологиях, в котором с этими же устройствами можно работать по протоколу MQTT.
Поэтому, если какие-либо улучшения или поддержка новых zigbee-устройств происходит в проекте Zigbee2MQTT, то можно перенести и добавить этот же функционал в этот драйвер. Если заметили это, то напиши issue - перенесем.

## Changelog

### 1.1.1 (2020-04-17)
* (kirovilya) Critical. Fixed error starting adapter if cc-chip was only flashed
* (kirovilya) Nue/3A FNB56-ZSW02LX2.0
* (Strunzdesign) Added missing raw button events for Philips Hue Smart Button ROM001
* (Sacred-Shadow) Fix Color for Outdoor Lantern W RGBW OSRAM

### 1.1.0 (2020-04-12)
new Zigbee-herdsman features:
* ConBee/RaspBee (experimental support) https://github.com/Koenkk/zigbee-herdsman/issues/72
* OTA update for some devices (IKEA, OSRAM and other) https://github.com/Koenkk/zigbee2mqtt/issues/2921
* Touchlink reset and join https://github.com/Koenkk/zigbee2mqtt/issues/2396
* Green Power devices support https://github.com/Koenkk/zigbee2mqtt/issues/3322
* (peterfido) iCasa KPD14S und KPD18S hinzu
* (kirovilya) Moes Zigbee Thermostatic Radiator
* (kirovilya) LifeControl power plug MCLH-03, bulb MCLH-02, water leak MCLH-07, door sensor MCLH-04
* (kirovilya) Philips LCT002, LCT011, LTW015, LWG004
* (kirovilya) Gledopto GL-C-007 with with channel
* (MultivitaminJuice) Iluminize 511.040
* (Sacred-Shadow) Bitron 902010/24
* (kirovilya) Color indication of LQI and Battery icon
* (kirovilya) Device info modal dialog
* (arteck) Philips LCT026
* (obakuhl) Improvements Osram switch mini
* (arteck) Nue / 3A FB56+ZSW1GKJ2.5, LXN-1S27LX1.0
* (agross) Philips Signe Floor and Table
* (arteck) TRADFRI bulb E14 WS 470lm, OSRAM PAR16 TW Z3
* (kirovilya) Smart remote controller (4 buttons)
* (allofmex) OTA updates
* (kirovilya) Aqara opple change mode keys (for binding)
* (palsch) Heiman HS2WD-E siren

### 1.0.4 (2020-03-14)
* (kirovilya) Philips Hue Adore Bathroom Mirror Light
* (kirovilya) Oujiabao Gas and carbon monoxide alarm
* (kirovilya) Tuya SOS button
* (Erdnuss3003) Schwaiger ZBT-DIMLight-GLS0800
* (arteck) Smart Home Pty FB56-ZCW11HG1.4, LXT56-LS27LX1.7
* (arteck) Xiaomi plug lumi.plug.mmeu01
* (arteck) Innr RS 228 T, RS 230 C
* (arteck) Gledopto GL-MC-001, GL-D-003ZS
* (allmyjoes) Bitron AV2010/21A
* (arteck) Osram Panel TW 595 UGR22
* (kirovilya) IKEA SURTE door WS 38x64
* (andigandi) Philips Hue LCG002, Hue LTG002
* (arteck) iCasa ICZB-FC
* (arteck) Osram A60 DIM Z3
* (arteck) Paulmann 371000001
* (DaCHRIS) Osram PAR16 DIM Z3
* (DaCHRIS) Philips LWG001
* (DaCHRIS) Illuminize 511.202
* (SchumyHao) TERNCY-SD01 knob dimmer
* (SchumyHao) Xiaomi lumi.lock.aq1
* (kirovilya) New eWeLink devices: button, TH sensor, contact sensor, motion sensor
* (kirovilya) Allow pairing to routers (again)
* (Erdnuss3003) Philips Hue LCT021
* (root) Trust ZWLD-100 water leak sensor
* (smartpran) Bitron AV2010/32

### 1.0.3 (2020-02-09)
* (Tw1nh34d) Hornbach FLAIR LED
* (asgothian) Hue smart button, Heiman smoke sensor
* (kirovilya) Philips LTC014, LTC015
* (kirovilya) Power states for QBKG11LM
* (Garfonso) Change role for occupancy state to 'sensor.motion'
* (kirovilya) Change illuminance state to illuminance_lux (for lux value)
* (arteck) Philips LCF002
* (arteck) TRADFRI open/close remote
* (kirovilya) Tuya sensor TS0201

### 1.0.2 (2020-01-29)
* (kirovilya) All button events for Aqara Opple switch
* (ma-john) OSRAM PAR16 RGBW Z3
* (arteck) Phillips LWA004
* (MiniMe6666) Heiman SmokeSendor-N-3.0
* (kirovilya) Force remove device
* (kirovilya) Fix some networkmap bugs
* (kirovilya) Extended info button
* (kirovilya) Long press for WXKG01LM

### 1.0.1 (2020-01-23)
* fix for old z-stack firmware

### 1.0.0 (2020-01-22)
* Powered by new [zigbee-herdsman](https://github.com/Koenkk/zigbee-herdsman) library and new [converters database](https://github.com/Koenkk/zigbee-herdsman-converters)
* Drop support NodeJS 6
* Serialport 8.0.5 (in zigbee-herdsman)
* More new devices
* Some design update
* Binding

### freeze shepherd

### 0.11.5 (2019-10-26)
* (allofmex) Improved publish-to-zigbee queue
* (arteck) Gledopto GL-B-001Z
* (kirovilya) iHORN Temperature & humidity sensor
* (kirovilya) Trust ZLED-TUNE9, DIYRuZ contact, Lonsonho Plug
* (kirovilya) IKEA driver 30W
* (allofmex) Hue Smart Plug
* (arteck) LST004

### 0.11.4 (2019-09-30)
* (Asgothian) Danalock V3 BTZB
* (Asgothian) GroupErrorInGetDevices
* (Asgothian) new Dev Innr RB 245
* (Asgothian) new Dev RS 225
* (Asgothian) new Dev Heiman COSensor
* (Asgothian) Improved device configuration method
* (Stabilostil) Fix for install error if running zigbee-adapter is updated

### 0.11.3 (2019-09-11)
* (kirovilya) Update Z-Stack 3 compatible
* (kirovilya) Restore lumi.sensor_ht
* (kirovilya) OSRAM SMART+ spot GU5.3 tunable white #340
* (allofmex) Temperature and illuminance calibration added for hue motion sensors
* (kirovilya) new Trust lamp
* (kirovilya) DiY 20 button keypad (http://modkam.ru/?p=1114)
* (kirovilya) Xiaomi/Aqara: double click for b186acn01, Hold and Shake state for some switch
* (kirovilya) Hieman HS2SK, Tuya temperature sensor
* (kirovilya) Konke: button, temperature, contact, motion

### 0.11.2 (2019-06-29)
* (allofmex) Hue sml sensitivity, Hue motion sensitivity
* (arteck) Innr RB 250 C, Gledopto GL-D-003Z, GL-G-001Z, GL-FL-004TZ, Philips LPT001
* (kirovilya) OSRAM CLA60 RGBW Z3, Xiaomi curtain ZNCLDJ11LM
* (kirovilya) Implement a time response for some xiaomi devices
* (arteck) Heiman smoke sensor, TRADFRI bulb E14 WS opal 600lm, Innr RB265

### 0.11.1 (2019-06-15)
* fix wrong initial extPanID. Sorry that need to repairing all devices again.
* fix code for aqara cube

### 0.11.0 (2019-06-14)
* Support both Z-Stack 1.2 and 3.0 [coordinator firmware](https://github.com/Koenkk/Z-Stack-firmware/tree/master/coordinator)
* Serialport 7.1.5
* (arteck) Adjustable time for pairing
* (kirovilya) Additional xiaomi plug states and decoupled mode for xiaomi wall switches
* (kirovilya) New DIY devices [ZigUP](https://github.com/formtapez/ZigUP) and [DIYRUZ_R4_5](http://modkam.ru/?p=1054)
* (arteck) JIAWEN FB56-ZCW08KU1.2, Nue / 3A FNB56-ZCW25FB1.9, HOMA1031, Trust CSW_ADUROLIGHT
* (allofmex) security update
* (allofmex) brightness fix
* (Asgothian) Osram Gardenpole Mini
* (Asgothian) Innr Plugs (BY 265 C, BY 165 C, RB265
* (Asgothian) Fix for Ikea Tradfri repeater (image)
* (sonntam) tint enhancements
* (stream2me) support for Danalock V3

### 0.10.3 (2019-03-27)
* fixes
* (kirovilya) Aqara Wireless Relay Controller, Smart LED Driver
* (asgothian) eCozy Thermostat, Nue / 3A, Gledopto GL-C-006 GL-C-009, Philips SML002, OSRAM Outdoor Lantern W RGBW, TRADFRI motion sensor
* (arteck) sensor_86sw2 new states
* (allofmex) Improved device configuration and network map
* (allofmex) security update
* (allofmex) brightness fix

### 0.10.2 (2019-03-15)
* some fixes
* (allofmex) Visualize mesh newtwork map, "available" state, configuration requests
* (Apollon77) Update test framework
* (sonntam) Tint remote
* (arteck) OSRAM Lightify Switch Mini, rwl021 dimmer
* (asgothian) TRADFRI signal repeater, Innr SP 120, Xiaomi Gas detector

### 0.9.2 (2019-02-25)
No support of node.js 4 any more
* (bluefox) Xiaomi Lock was added
* (nisiode) Some fixes
* (sonntam) Some fixes
* (arteck) Heiman SmokeSensor
* (asgothian, allofmex) Eurotronic support

### 0.9.1 (2019-01-29)
* Groups and new Developer tab were added

### 0.9.0 (2019-01-28)
* (arteck) Many new devices
* (allofmex) Developer tab
* (modmax) Reading attributes
* (kirovilya) Groups support

### 0.8.0 (2018-11-29)

**BREAKING CHANGES**:
* (kirovilya) Rename state "isopen" to "opened".
* (kirovilya) Change brightness interval from 0..254 to 0..100

Other changes:
* (kirovilya) Fix for admin2
* (kirovilya) + Gledopto
* (kirovilya) + Mijia vibration sensor
* (kirovilya) Common state "link_quality"
* (arteck) + Philips LLC010, LLC011, LLC012, LTW001, LTW004, LTW010, LTW012, LTC001, LCT024
* (arteck) + Osram PAR 16 50 RGBW - LIGHTIFY
* (arteck) + Innr RS 128 T, RS 185 C
* (arteck) + DE FLS-PP3
* (arteck) + Ilux LEColorLight
* (kirovilya) Light state "transition_time" for brightness, color, colortemp


### 0.7.7 (2018-10-21)
* (arteck) Fix 'is open' state

### 0.7.6 (2018-10-19)
* (kirovilya, arteck) New models and devices

### 0.7.5 (2018-10-02)
* (kirovilya) Support zigbee-shepherd-converters 4.*

### 0.7.4 (2018-10-01)
* (kirovilya) Allow enter port without selector

### 0.7.3 (2018-09-27)
* (arteck) Bugfix and new devices: Classic A60 W clear - LIGHTIFY and Surface Light TW
* (kirovilya) Occupancy timeout state for motion sensor
* (kirovilya) Serialport selector

### 0.7.1 (2018-08-14)
* (kirovilya) Network map feature
* (kirovilya) Allow pairing through router
* (kirovilya) Change battery percent interval to 2700..3200
* (arteck) New devices: Hue LTW010, Osram Flex RGBW
* (kirovilya) Triple and quadruple clicks for WXKG11LM
* (kirovilya) isopen - magnet state, in contrast to contact
* (kirovilya) Option "Disable LED for cc2531"

### 0.6.0 (2018-07-05)
* (kirovilya) More new devices from zigbee-shepherd-converters
* (kirovilya) Some layout fixes in admin
* (kirovilya) Fix battery for smoke sensor

### 0.5.9 (2018-06-27)
* (arteck) New devices: Osram LED PAR16, Osram Smart+ plug, Philips Hue bulb
* (kirovilya) Turn on/off lights when change brightness > 0 and = 0

### 0.5.8 (2018-06-26)
* (kirovilya) Allow backup/restore zigbee-database for js-controller 1.5.0
* (kirovilya) New device - Jiawen bulb
* (kirovilya) Allow remove device with setup key
* (from zigbee-shepherd-converters) Change battery percent interval to 3000-2700

### 0.5.7 (2018-06-19)
* (kirovilya) Update states on adapter start (for restored shepherd.db)
* (kirovilya) Brightness - not percent - range 0..255

### 0.5.6 (2018-06-14)
* (kirovilya) Configuration panID (zigbee network identifier)
* (kirovilya) Moved to ioBroker organization

### 0.5.5 (2018-06-11)
* (kirovilya) Return runing on NodeJS 4.*

### 0.5.4 (2018-06-10)
* (kirovilya) Public version

### 0.5.0 (2018-06-06)
* (kirovilya) All refactored

### 0.0.1 (2018-02-07)
* (kirovilya) First version

## License
The MIT License (MIT)

Copyright (c) 2018-2020 Kirov Ilya <kirovilya@gmail.com>

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