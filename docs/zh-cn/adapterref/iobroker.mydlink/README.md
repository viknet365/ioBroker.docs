---
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.mydlink/README.md
title: ioBroker.mydlink
hash: yp3apFNnqC6pOAs2BrgvJs4GL5Sw984Xz6MPKoWgIbc=
---
![商标](../../../en/adapterref/iobroker.mydlink/admin/mydlink.png)

![安装数量](http://iobroker.live/badges/mydlink-stable.svg)
![NPM版本](http://img.shields.io/npm/v/iobroker.mydlink.svg)
![资料下载](https://img.shields.io/npm/dm/iobroker.mydlink.svg)
![测验](https://travis-ci.org/iobroker-community-adapters/ioBroker.mydlink.svg?branch=master)
![NPM](https://nodei.co/npm/iobroker.mydlink.png?downloads=true)
![环保管理员徽章](https://badges.greenkeeper.io/iobroker-community-adapters/ioBroker.mydlink.svg)

＃ioBroker.mydlink
ioBroker的MyDlink适配器。
-------------------------------------------------- ----------------------------

允许从ioBroker中的[D-Link](https://eu.dlink.com/uk/en/for-home/smart-home)控制电源插座或运动检测器。

**此适配器使用Sentry库自动向开发人员报告异常和代码错误。**有关更多详细信息以及如何禁用错误报告的信息，请参阅[哨兵插件文档](https://github.com/ioBroker/plugin-sentry#plugin-sentry)！ Sentry报告从js-controller 3.0开始使用。
这也有助于支持新设备。

当前测试的设备：

|型号|类型图片|
| :---: | :---: | :---: |
| DSP-W215 |智能插头（插座，温度，电流）**需要轮询** | ![图片](../../../en/adapterref/iobroker.mydlink/admin/DSP_W215.png)|
| DCH-S150 |动作检测器（检测到最后动作）**需要轮询** | ![图片](../../../en/adapterref/iobroker.mydlink/admin/DCH_S150.png)|
| DCH-S150 |动作检测器（检测到最后动作）**需要轮询** | ！[Image]（admin / DCH_S150.png）|

适配器需要轮询某些设备。较新的确实会发送推送消息，现在支持该消息。如果需要对传感器读数和运动检测进行轮询（可以在配置中进行设置），则会通过轮询间隔来延迟它们。

####配置：
*设备列表，每个设备具有以下设置：

<table><tr><td>名称</td><td>在此处设置名称，必须唯一（对于mydlink设备） </td></tr><tr><td>知识产权</td><td>在此处填写IP地址，主机名也应该有效</td></tr><tr><td>销</td><td> PIN码印在设备的不干胶标签上，可能在底部。可以是用于DSP-W115的TELNET，请参见下文。 </td></tr><tr><td>轮询间隔</td><td>每个设备的轮询间隔<br />设置为0以禁用轮询。 <br /> <b>建议：</b>为传感器设置一个快速轮询间隔，为插头设置一个较长的轮询间隔。 </td></tr><tr><td>使能</td><td>如果未启用，将不会被轮询或控制。 <br />可以禁用未插入的设备，以避免网络流量和日志中的错误消息。 </td></tr></table>

适配器不会干扰应用程序的使用。

##设置DSP-W115
其他*较新的*设备使用完全不同的协议和不同的设置。如果您从mydlink应用程序中删除设备，则可以将它们用作其他设备并输入常规PIN码。

如果要继续使用该应用程序，则必须按照以下步骤将设备置于出厂模式：

1.在启动过程中按住wps / reset按钮将设备重置为恢复模式，直到它开始闪烁**红色**而不是橙色。
2.现在正在运行telnet守护进程，连接到设备wifi
3.运行“ telnet 192.168.0.20”并使用“ admin：123456”登录（或使用腻子，不要忘记选择“ telnet”而不是“ ssh”）。
4.运行“ nvram_set FactoryMode 1”
5.运行`reboot;退出；`重新启动设备。

现在，您应该输入`TELNET`作为Pin，适配器将从设备本身检索所需的数据。

## Changelog
<!-- 
	Placeholder for next versions (this needs to be indented):
	### __WORK IN PROGRESS__
-->
### 1.1.2 (2020-06-01)
* fixed two possible crashes with offline / wrong devices.

### 1.1.1 (2020-06-01)
* Improved auto detection of DSP-W115 (but mdns seems very unreliable whit that device)
* UI should never delete user devices

### 1.1.0 (2020-05-31)
* Added Support for w115 (and maybe other never myDlink devices, might even do *something* with cameras)
* Fix relogin to device (i.e. when device was restarted during adapter runtime) 
* Fix error when switching a socket.

### 1.0.11 (2020-05-10)
* Tried to add even more information in case device seems incompatible

### 1.0.10 (2020-05-10)
* Returned to login with user "Admin"
* Tried to add more debug for incompatible devices.

### 1.0.9 (2020-05-07)
* Fixed: changes in configuration were not respected once devices were created
* Fixed: re-login to device on switching if polling is disabled
* Fixed: Error output on switching now more informative

### 1.0.8 (2020-05-05)
* Fixed switching, was broken in some circumstances by id changes.

### 1.0.7 (2020-05-02)
* Made saving config more robust and direct again.
* Made identify by IP more robust and allows saving right away. 
* Prevent saving if devices without PIN are configured.

### 1.0.6 (2020-05-02)
* Prevent creation of empty devices (MYDLINK-6)

### 1.0.5 (2020-05-02)
* Fixed possible issue with device ids.
* Improved device creation
* Adjusted for discovery adapter that not yet stores passwords encrypted.

### 1.0.4 (2020-05-01)
* Improved connection keepAlive
* Improved logging of network errors

### 1.0.3 (2020-05-01)
* Fixed login/identification loop on (possibly) duplicate devices

### 1.0.2 (2020-04-30)
* Fixed potential crashes on network errors.

### 1.0.1 (2020-04-30)
* Re-added device config to adapter config (in case objects get deleted).

### 1.0.0 (2020-04-30)
* BREAKING CHANGE: device id is now mac instead of name -> all devices need to be recreated. Sorry for that. But should never happen again, now. New devices *should* be created automatically.
* added encryption of PIN
* settings stored in native part of device (please do not delete them or you have to reconfigure them)
* modified device creation / identification / start to allow devices to be (re-)started during runtime (you do not need to press save on config page anymore)
* added auto detection
* added missing translations
* added sentry plugin (including sending information about unknown devices)
* a lot of internal restructuring and cleanup for better maintenance in future.

### 0.0.7
* (Garfonso) added info.connection state
* (Garfonso) suppressed repeated error messages during polling.

### 0.0.6
* (Garfonso) prevent removement of custom details in objects.

### 0.0.5
* (Garfonso) fixed config files for release in latest repository.

### 0.0.4
* (Garfonso) polling interval can now be configured on per device basis (if not configured for a device global poll intervall will be used.) Recommendation: Use high global poll interval and a smaller one for motion detectors.
* (Garfonso) added no_motion state for motion detectors, contains number of seconds since last motion.

### 0.0.3
* (Garfonso) use setStateChanged instead of polling state before writing.
* (Garfonso) minor clean ups.

### 0.0.2
* (Garfonso) move to ioborker-community-adapters

### 0.0.1
* (Garfonso) initial release

## License
MIT License

Copyright (c) 2020 Garfonso <garfonso@mobo.info>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.