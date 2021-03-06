# IPSymconHomepilot
===

Modul für IP-Symcon Version 4.0 ermöglicht die Kommunikation mit dem Rademacher Homepilot.

## Dokumentation

**Inhaltsverzeichnis**
 ab
1. [Funktionsumfang](#1-funktionsumfang)  
2. [Voraussetzungen](#2-voraussetzungen)  
3. [Installation](#3-installation)  
4. [Funktionsreferenz](#4-funktionsreferenz)
5. [Konfiguration](#5-konfiguration)  
6. [Anhang](#6-anhang) 

## 1. Funktionsumfang

Das Modul liest die Konfiguration des Homepilot aus und erstellt automatisch in IP-Symcon die vorhandenen Instanzen mit Schaltmöglichkeiten im Webfront.

[Homepilot Rademacher](https://homepilot.rademacher.de/ "Homepilot Rademacher")

## 2. Voraussetzungen

 - IPS 4.0
 - Rademacher Homepilot

## 3. Installation

### a. Laden des Moduls

 Wir wechseln zu IP-Symcon (min Ver. 4.0) und fügen unter Kerninstanzen über __*Modules*__ -> Hinzufügen das Modul hinzu mit der URL
```
https://github.com/Alexxx2005/IPSymconHomepilot
```	

### b. Einrichtung in IPS

1. Unter Splitter Instanzen im Symcon fügt man unter Objekt Hinzufügen eine neue Instanz und wählt als Gerät den __Homepilot Splitter__ aus. 
2. Es wird ein Splitter mit der dazugehörigen __Homepilot I/O__ angelegt. 
3. Als nächstes wird im Objektbaum eine neue Kategorie erstellt in der später die Homepilot Geräte angelegt werden sollen.
4. Unter __I/O Instanzen__ wählr man den __HomepilotIO__ aus und ergänzt die IP-Adresse des Homepiloten. Ebenso trägt man im Formular die zuvor erstellte Kategorie ein und bestätigt mit _übernehmen_ . Im unteren Teil des Formulars wählt man zunächst _Konfiguartion auslesen_ aus und im Anschluss _Setup Homepilot_ . Nun werden die Geräte in IP-Symcon angelegt. An den Geräte Instanzen ist nichts zusätzlich zu konfigurieren diese sollten nach dem Anlegen über den Webfront bedienbar sein.

## 4. Funktionsreferenz

### Homepilot
Ein Gerät wird mit der entsprechenden Funktion und Übergabe der InstanzID angesteuert.
 
Rollladen Hochfahren
```php
Homepilot_Up(integer $InstanceID)
```   
Parameter _$InstanceID_ __*ObjektID*__ der Homepilot Instanz

Rollladen Stop
```php
Homepilot_Stop(integer $InstanceID)
```   
Parameter _$InstanceID_ __*ObjektID*__ der Homepilot Instanz

Rollladen Runterfahren
```php
Homepilot_Down(integer $InstanceID)
```   
Parameter _$InstanceID_ __*ObjektID*__ der Homepilot Instanz

Rollladen Position 0 % anfahren
```php
Homepilot_Position0(integer $InstanceID)
```   
Parameter _$InstanceID_ __*ObjektID*__ der Homepilot Instanz

Rollladen Position 25 % anfahren
```php
Homepilot_Position25(integer $InstanceID)
```   
Parameter _$InstanceID_ __*ObjektID*__ der Homepilot Instanz

Rollladen Position 50 % anfahren
```php
Homepilot_Position50(integer $InstanceID)
```   
Parameter _$InstanceID_ __*ObjektID*__ der Homepilot Instanz

Rollladen Position 75 % anfahren
```php
Homepilot_Position75(integer $InstanceID)
```   
Parameter _$InstanceID_ __*ObjektID*__ der Homepilot Instanz

Rollladen Position 100 % anfahren
```php
Homepilot_Position100(integer $InstanceID)
```   
Parameter _$InstanceID_ __*ObjektID*__ der Homepilot Instanz

Rollladen Position X % anfahren
```php
Homepilot_Position(integer $InstanceID, integer $position)
```   
Parameter _$InstanceID_ __*ObjektID*__ der Homepilot Instanz
Parameter _$position_ Anzufahrende __*Position*__ des Rollladen


### Homepilot IO
Konfiguration auslesen
```php
HomepilotIO_getConfig(integer $InstanceID)
```   
Parameter _$InstanceID_ __*ObjektID*__ der Homepilot I/O Instanz

Holt die aktuelle Position vom Homepilot ab und schreibt diese in die Instanz Variable des Rollladens
```php
HomepilotIO_GetState(integer $InstanceID)
```   
Parameter _$InstanceID_ __*ObjektID*__ der Homepilot I/O Instanz
 

## 5. Konfiguration:

### Homepilot IO:

| Eigenschaft       | Typ     | Standardwert | Funktion                                                  |
| :---------------: | :-----: | :----------: | :-------------------------------------------------------: |
| Host              | string  | 		     | IP Adresse des Homepilot                                  |
| ImportCategoryID  | integer | 		     | ObjektId der Importkategorie für die Homepilot Geräte     |
| username          | string  | 		     | username                                                  |
| password          | string  |              | password                                                  |



### Homepilot:  

| Eigenschaft      | Typ     | Standardwert| Funktion                                                    |
| :--------------: | :-----: | :---------: | :---------------------------------------------------------: |
| Name             | string  |             | Name des Geräts                                             |
| DeviceID         | integer |             | Device ID des Geräts                                        |
| ProductName      | string  |             | Produktbezeichnung                                          |
| Version          | string  |             | Version des Geräts                                          |
| UID              | string  |             | UID des Geräts                                              |





## 6. Anhang

###  a. GUIDs und Datenaustausch:

#### Homepilot IO:

GUID: `{D40B39AA-3966-41F1-A7E1-ABFF538DE0CE}` 


#### Homepilot:

GUID: `{19E9190A-F772-4589-8655-5FB219F6C418}` 


