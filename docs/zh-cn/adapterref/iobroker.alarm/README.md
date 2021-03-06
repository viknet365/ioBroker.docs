---
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.alarm/README.md
title: ioBroker.alarm
hash: HtQRzGke7pLNpCxorf6Re5gBtRVUr7f+kyqVQrsWrJU=
---
![商标](../../../en/adapterref/iobroker.alarm/admin/alarm.png)

![安装数量](http://iobroker.live/badges/alarm-stable.svg)
![NPM版本](http://img.shields.io/npm/v/iobroker.alarm.svg)
![资料下载](https://img.shields.io/npm/dm/iobroker.alarm.svg)
![依赖状态](https://img.shields.io/david/misanorot/iobroker.alarm.svg)
![已知漏洞](https://snyk.io/test/github/misanorot/ioBroker.alarm/badge.svg)
![NPM](https://nodei.co/npm/iobroker.alarm.png?downloads=true)
![特拉维斯](http://img.shields.io/travis/misanorot/ioBroker.alarm/master.svg)

＃ioBroker.alarm
[![贝宝（https://www.paypalobjects.com/zh_CN/DK/i/btn/btn_donateCC_LG.gif）](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=ZYHW84XXF5REJ&source=url)

**[英文说明](https://github.com/misanorot/ioBroker.alarm/blob/master/lib/Readme_en.md)**

## IoBroker警报
Dies ist ein Adapter，mit dem sich eine kleine Alarmanlage ohnegroßeprogrammiertechnische Vorkenntnisse realisierenlässt。
二等译成《死刑书》和《死刑书》 Nachtruhe oder De- und Aktivierung zuüberwachen。德斯坦·维特伦主义者·伊恩·迪内克特·德斯坦·威斯坦·因斯坦斯（州），安夫·安德烈（州）莫格利希。 DieseVerknüpfungenwerden im ReiterVeregnüpfungenangelegt。

-------------------------------------------------- -------------------------------------------------- ------------------ *站位28.05.2020 *

### Tab Haupteinstellungen
较高的等级，包括Zeiten der Nachtruhe，Sirenezeit，Stiller-Alarm和Passwort vorgenommen。

* Alle Zeiten在Sekunden einzugeben中犯罪*

-Aktivierzeit->Zeitverzögerungbis zu Aktivierung wenn man einen delay Datenpunkt benutzt
-Sienenzeit bei Einbruch-> Bei Einbruch wird der Datenpunkt alarm.0.status.sirenfürdie Zeit auf true gesetzt
-Alarmverzögerung->Verzögerungszeitbis Einbruchausgelöstwird（与瓦伦德·迪塞尔Zeit wird der Stille Alarmausgelöst）
-Warnungen的Auslösezeitit-> Warnkreise的BeiAuslösungeines der（详细信息）

----------------------------------------------------------------------------------------------------------------------

### Tab Benachrichtigungen
BenachrichtigungenüberAndere适配器wie z.B.电报，电子邮件或其他。
[问题](#Probleme)

----------------------------------------------------------------------------------------------------------------------

### TabÜberwachung
更高的werden die Kreise der Anlage konfiguriert。
*戴姆·德恩州立大学拉森学院

安拉格·沃尔格·沃伦·沃·艾伦·安德烈·基森和阿里奇·维克特·艾里克·德·艾尔格里克都在“优先”和“优先”的帽子上工作。

冯·芬奇根（Funktionen）的儿子，国家图书馆（Nurüberwachtund geben ggf）。 eine Meldung ab wenn eineÄnderungstattfand。 Die zweite Funktion besteht darin，bei z。 B.州立商业联合会（GGF）的内华达州立大学（内部十分尖锐）。 eine Meldung Abgesetzt wird。

Nachtkreis的帽子是Funktion wie der Warnkreis，Jedoch nurwährendder Nachtruhe。 Bei初学者Nachtruhelöst死亡，摔倒，死于Überwachungdes Warnkreises（内锋）。

* Es ist durchausmöglich，艾因州立大学，den Haken贝艾伦德雷·克雷森马克特。

Die Kreise sindfolgendermaßenüberwacht：

#### Alarmkreis：
阿兰基拉格州立社会主义主义者。您可以在警报器中查看警报。

#### Warnkreis：
könnenDingeüberwachtwerden die nicht diePriorität“ hoch” haben，z.B. Oen的Fenster。在d'Haupteinstellungen中，kann man死于Überwachungbei der Aktivierung einstellen。首先是警报器，然后是警报器。
曼·肯·希奇·杰多克·本纳奇·蒂根·拉森。

#### Nachtkreis：
Bei aktiver Nachtruhe werdenVeränderungenwährendder erkannt和ggf。宝石。

*Sollten Alarm-和Warnkreis专业州警察局，Zähltder Alarmkreis*

----------------------------------------------------------------------------------------------------------------------

### Tab Sprachausgabe
伊恩·盖恩施特（Est einegewünschte） bei beiÄnderungdes Zustandesgewünscht，sich das hier mit dengewünschtenSätzenkonfigurieren。
*曼·穆斯·希奇·谢尔森（Mus sich sicher sein），达斯·德·奥斯特瓦特·达滕彭克（das derausgewählteDatenpunkt），麻省理工学院的einem Text beschrieben werden kann！ Z.B. “ sayit.0.tts” *

曼彻斯特人（Ausgabe von Namen mit Ansagen拉森）

----------------------------------------------------------------------------------------------------------------------

### TabVerknüpfungen
等级较高的适配器州际直属州外部州zuverknüpfen。 Somit ist ein Umwegüberein Skript oderähnlichennicht erforderlich。
Eslässtsich somit z.B.在Nachtruhe的Beginn der出版社，Eure Veriegelung desTürschlosses的房地产。
![商标](../../../en/adapterref/iobroker.alarm/admin/img/short.png)

----------------------------------------------------------------------------------------------------------------------

Der Adapter liefert eine ganze Anzahl国家/地区：

####“ alarm.x.use .....”。
紧急状态下的警报和警报状态。
Es istmöglich死于Alarmanlage direkt von aktiviert auf“ intern scharf” umzuschalten，死于jedoch nurMöglichWenn死于Alarmanlage nicht奥斯特洛斯特。

-use.activate_nightrest-> Aktivierung der Nachtruhe
-use.deactivate_nightrest-> Deaktivierung der Nachtruhe
-use.toggle_nightrest-> Deaktivierung / Aktivierung der Nachtruhe
-use.activate_warn_circuit->战役实习生（实习生）
-use.deactivate_warn_circuit-> Warnkreises的实习生（实习生）
-use.toggle_warn_circuit-> Deaktivierung / Arktivierung der Warkreises（实习生）
-use.disable-> Deaktivierung der Anlage（Alarmkreis）
-use.enable-> Aktivierung der Anlage（Alarmkreis）
-use.enable_with_delay->安提格（Alarmkreis）博物馆（Verzögerungszeit）
-use.list-> Deaktivierung / Aktivierung / Warnkreis / Aktivierung mitVerzögerungszeit
-use.quit_changes->贝登州立大学（Rücksetzender beiden）* info.warn / night_circuit_changes *
-use.toggle-> Deaktivierung / Aktivierung der Anlage（Alarmkreis）
-use.toggle_password-> Deaktivierung / Aktivierung der Anlage（Alarmkreis）mit Passwort
-use.toggle_with_delay-> Deaktivierung / Aktivierung der Anlage（Alarmkreis）mitVerzögerungszeit
-use.toggle_with_delay_and_password-> Dealtivierung / Aktivierung der Anlage（Alarmkreis）mit Passwort undVerzögerungszeit
-use.panic->HändischeAuslösungder Alarmanlage（Einbruch）

####“ alarm.x.status ....”
尊贵的祖斯塔德·安拉格能力等级较高的人。

####“ alarm.x.info ....”
LiefertzusätzlicheInformationen wie z.B. welche“Türenoffen sind” oder einen日志状态。
由Mitternacht Geleert提供的log_today状态。

----------------------------------------------------------------------------------------------------------------------

##问题
-温恩·曼恩（Wen man eine）的电报，德国坎斯坦·曼努尔州州立大学（Instanzauswählen）和曼斯·穆斯·比斯·奥夫（tesgram）* telegram.0 * alleslöschen。

#### Wichtig，死于Benutzung，死于适配器。

## Changelog

#### 0.7.0 (07.06.2020)
* (misanorot) edit notification sentences in admin

#### 0.6.0 (31.05.2020)
* (misanorot) changed speech output

#### 0.5.0 (14.05.2020)
* (misanorot) added use.list state

#### 0.4.0 (14.05.2020)
* (misanorot) added warn circuit monitoring

#### 0.3.0 (04.05.2020)
* (misanorot) expaned speech output

#### 0.2.2 (30.04.2020)
* (misanorot) added alexa2 speak output

#### 0.2.0 (22.04.2020)
* (misanorot) added more states

#### 0.1.2 (19.04.2020)
* (misanorot) status.state  activated

#### 0.1.1 (28.03.2020)
* (misanorot) added states and lists - fixed issues - translation

#### 0.1.0 ()
* (misanorot) add password for de/activation -- better logging

#### 0.0.9 (19.02.2020)
* (misanorot) add sayit

#### 0.0.8 (03.02.2020)
* (misanorot) initial release

## License
MIT License

Copyright (c) 2019-2020 misanorot <audi16v@gmx.de>

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