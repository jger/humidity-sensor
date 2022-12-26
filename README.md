# HygraSense 
Tasmota portable humidity and temprature sensor with display 

<img src="/photos/hardware2.jpg" alt="HygraSense" height="260"/><img src="/photos/hygrasense-in-box.jpg" alt="HygraSense" height="260"/>

## Hardware 

#### D1 ESP8266
D1 from [amazon](https://www.amazon.de/-/en/gp/product/B0754N794H) (4€*)

#### Battery / LiPo Shield for D1 Mini
Shield from [berrybase](https://www.berrybase.de/battery/lipo-shield-fuer-d1-mini) (3.25€*)

Battery from [berrybase](https://www.berrybase.de/lp-503035-lithium-polymer/lipo-akku-3-7v-500mah-mit-2-pin-jst-stecker) (4.50€*)

Female ph2 2 pin connector from [berrybase](https://www.berrybase.de/en/ph2.0-buchse-printmontage-gewinkelt-2-pin) (0.07€*)

#### 0.66" OLED Display Shield for D1 Mini
Display from [berrybase](https://www.berrybase.de/0.66-oled-display-shield-fuer-d1-mini) (4.90€*)

* Prices from December 2022

## Configuration

### Tasmota -> Configuration -> Configure Module
<img src="/photos/module-configuration.png" alt="tasmota module configuration" width="300"/>

### Tasmota ->  Configuration -> Configure Logging
<img src="/photos/logging-configuration.png" alt="tasmota logging configuration" width="300"/>

### Tasmota -> Console
Following rulles must setup. You must enter the following commands:

#### Set display mode to 0 (custom)
```
displaymode 0
```

#### Show sensor readings
```
rule1 on tele-AM2301#Temperature do DisplayText [C0B1s1x36y18]%value%~20~20~20[C0B1s1x69y20k1][C0B1s1x71y18]C endon
      on tele-AM2301#Humidity do DisplayText [C0B1s1x36y32]%value% %~20~20~20 endon
      on tele-AM2301#Humidity do DisplayText [C0B1s1x36y50tS]~20~20 endon
```      
      
#### Clear display on boot and show logo
```
rule2 on System#Boot do displaytext [zC0B1zs1x36y18]Hygra[s1x36y32]~20~20~20sense [s1x58y50]v.1.0 endon      
```

#### Set rule 1 on 
```
rule1 1
```

#### Set rule 2 on 
```
rule2 1
```


## 3d printed case 

#### You can print the following 2 files to create a box for this device.

[HS-box.stl](/3d-printing/HS-box.stl)

[HS-top.stl](/3d-printing/HS-top.stl)

