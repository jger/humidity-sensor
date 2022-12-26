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

```stl
solid ASCII
  facet normal -0.000000e+00 1.000000e+00 0.000000e+00
    outer loop
      vertex   2.685000e+01 -2.077545e+01 3.600000e+01
      vertex   3.135000e+01 -2.077545e+01 3.600000e+01
      vertex   2.773163e+01 -2.077545e+01 3.100000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 1.000000e+00 0.000000e+00
    outer loop
      vertex   2.773163e+01 -2.077545e+01 3.100000e+01
      vertex   3.135000e+01 -2.077545e+01 3.600000e+01
      vertex   3.046836e+01 -2.077545e+01 3.100000e+01
    endloop
  endfacet
  facet normal -9.848078e-01 0.000000e+00 -1.736482e-01
    outer loop
      vertex   2.685000e+01 -3.077545e+01 3.600000e+01
      vertex   2.685000e+01 -2.077545e+01 3.600000e+01
      vertex   2.773163e+01 -3.077545e+01 3.100000e+01
    endloop
  endfacet
  facet normal -9.848078e-01 -3.498740e-16 -1.736482e-01
    outer loop
      vertex   2.773163e+01 -3.077545e+01 3.100000e+01
      vertex   2.685000e+01 -2.077545e+01 3.600000e+01
      vertex   2.773163e+01 -2.077545e+01 3.100000e+01
    endloop
  endfacet
  facet normal -0.000000e+00 -1.000000e+00 0.000000e+00
    outer loop
      vertex   3.135000e+01 -3.077545e+01 3.600000e+01
      vertex   2.685000e+01 -3.077545e+01 3.600000e+01
      vertex   3.046836e+01 -3.077545e+01 3.100000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 -1.000000e+00 0.000000e+00
    outer loop
      vertex   3.046836e+01 -3.077545e+01 3.100000e+01
      vertex   2.685000e+01 -3.077545e+01 3.600000e+01
      vertex   2.773163e+01 -3.077545e+01 3.100000e+01
    endloop
  endfacet
  facet normal 9.848078e-01 0.000000e+00 -1.736482e-01
    outer loop
      vertex   3.135000e+01 -2.077545e+01 3.600000e+01
      vertex   3.135000e+01 -3.077545e+01 3.600000e+01
      vertex   3.046836e+01 -2.077545e+01 3.100000e+01
    endloop
  endfacet
  facet normal 9.848078e-01 3.498740e-16 -1.736482e-01
    outer loop
      vertex   3.046836e+01 -2.077545e+01 3.100000e+01
      vertex   3.135000e+01 -3.077545e+01 3.600000e+01
      vertex   3.046836e+01 -3.077545e+01 3.100000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   3.046836e+01 -3.077545e+01 3.100000e+01
      vertex   2.773163e+01 -3.077545e+01 3.100000e+01
      vertex   3.046836e+01 -2.077545e+01 3.100000e+01
    endloop
  endfacet
  facet normal -0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   3.046836e+01 -2.077545e+01 3.100000e+01
      vertex   2.773163e+01 -3.077545e+01 3.100000e+01
      vertex   2.773163e+01 -2.077545e+01 3.100000e+01
    endloop
  endfacet
  facet normal -1.480297e-16 -1.000000e+00 4.440892e-17
    outer loop
      vertex   4.170000e+01 -1.600000e+00 3.100000e+01
      vertex   4.170000e+01 -1.600000e+00 3.600000e+01
      vertex   4.020000e+01 -1.600000e+00 3.100000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 -1.000000e+00 0.000000e+00
    outer loop
      vertex   4.020000e+01 -1.600000e+00 3.100000e+01
      vertex   4.170000e+01 -1.600000e+00 3.600000e+01
      vertex   4.020000e+01 -1.600000e+00 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 1.000000e+00 0.000000e+00
    outer loop
      vertex   4.170000e+01 -2.210000e+01 3.600000e+01
      vertex   4.170000e+01 -2.210000e+01 3.100000e+01
      vertex   4.020000e+01 -2.210000e+01 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 1.000000e+00 0.000000e+00
    outer loop
      vertex   4.020000e+01 -2.210000e+01 3.600000e+01
      vertex   4.170000e+01 -2.210000e+01 3.100000e+01
      vertex   4.020000e+01 -2.210000e+01 3.100000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   4.020000e+01 -1.600000e+00 3.100000e+01
      vertex   4.020000e+01 2.000000e-01 3.100000e+01
      vertex   4.170000e+01 -1.600000e+00 3.100000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   4.170000e+01 -1.600000e+00 3.100000e+01
      vertex   4.020000e+01 2.000000e-01 3.100000e+01
      vertex   4.170000e+01 1.700000e+00 3.100000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   4.170000e+01 1.700000e+00 3.100000e+01
      vertex   4.020000e+01 2.000000e-01 3.100000e+01
      vertex   -2.000000e-01 2.000000e-01 3.100000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   4.170000e+01 1.700000e+00 3.100000e+01
      vertex   -2.000000e-01 2.000000e-01 3.100000e+01
      vertex   -1.700000e+00 1.700000e+00 3.100000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   -1.700000e+00 1.700000e+00 3.100000e+01
      vertex   -2.000000e-01 2.000000e-01 3.100000e+01
      vertex   -1.700000e+00 -4.770000e+01 3.100000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   -1.700000e+00 -4.770000e+01 3.100000e+01
      vertex   -2.000000e-01 2.000000e-01 3.100000e+01
      vertex   -2.000000e-01 -4.620000e+01 3.100000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   -1.700000e+00 -4.770000e+01 3.100000e+01
      vertex   -2.000000e-01 -4.620000e+01 3.100000e+01
      vertex   4.020000e+01 -4.620000e+01 3.100000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   4.020000e+01 -2.210000e+01 3.100000e+01
      vertex   4.170000e+01 -2.210000e+01 3.100000e+01
      vertex   4.020000e+01 -4.620000e+01 3.100000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   4.020000e+01 -4.620000e+01 3.100000e+01
      vertex   4.170000e+01 -2.210000e+01 3.100000e+01
      vertex   4.170000e+01 -4.770000e+01 3.100000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 -0.000000e+00 -1.000000e+00
    outer loop
      vertex   4.020000e+01 -4.620000e+01 3.100000e+01
      vertex   4.170000e+01 -4.770000e+01 3.100000e+01
      vertex   -1.700000e+00 -4.770000e+01 3.100000e+01
    endloop
  endfacet
  facet normal -1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   4.020000e+01 -2.210000e+01 3.100000e+01
      vertex   4.020000e+01 -4.620000e+01 3.100000e+01
      vertex   4.020000e+01 -2.210000e+01 3.600000e+01
    endloop
  endfacet
  facet normal -1.000000e+00 -0.000000e+00 0.000000e+00
    outer loop
      vertex   4.020000e+01 -2.210000e+01 3.600000e+01
      vertex   4.020000e+01 -4.620000e+01 3.100000e+01
      vertex   4.020000e+01 -4.620000e+01 3.600000e+01
    endloop
  endfacet
  facet normal -1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   4.020000e+01 -1.600000e+00 3.600000e+01
      vertex   4.020000e+01 2.000000e-01 3.600000e+01
      vertex   4.020000e+01 -1.600000e+00 3.100000e+01
    endloop
  endfacet
  facet normal -1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   4.020000e+01 -1.600000e+00 3.100000e+01
      vertex   4.020000e+01 2.000000e-01 3.600000e+01
      vertex   4.020000e+01 2.000000e-01 3.100000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   2.685000e+01 -2.077545e+01 3.600000e+01
      vertex   2.800000e+01 -1.630000e+01 3.600000e+01
      vertex   3.135000e+01 -2.077545e+01 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   3.135000e+01 -2.077545e+01 3.600000e+01
      vertex   2.800000e+01 -1.630000e+01 3.600000e+01
      vertex   4.020000e+01 -1.600000e+00 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   3.135000e+01 -2.077545e+01 3.600000e+01
      vertex   4.020000e+01 -1.600000e+00 3.600000e+01
      vertex   4.020000e+01 -2.210000e+01 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   4.020000e+01 -2.210000e+01 3.600000e+01
      vertex   4.020000e+01 -1.600000e+00 3.600000e+01
      vertex   4.170000e+01 -1.600000e+00 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   4.020000e+01 -2.210000e+01 3.600000e+01
      vertex   4.170000e+01 -1.600000e+00 3.600000e+01
      vertex   4.170000e+01 -2.210000e+01 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   2.685000e+01 -3.077545e+01 3.600000e+01
      vertex   2.260000e+01 -2.960000e+01 3.600000e+01
      vertex   2.685000e+01 -2.077545e+01 3.600000e+01
    endloop
  endfacet
  facet normal -0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   2.685000e+01 -2.077545e+01 3.600000e+01
      vertex   2.260000e+01 -2.960000e+01 3.600000e+01
      vertex   2.260000e+01 -1.700000e+01 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   2.685000e+01 -2.077545e+01 3.600000e+01
      vertex   2.260000e+01 -1.700000e+01 3.600000e+01
      vertex   2.800000e+01 -1.630000e+01 3.600000e+01
    endloop
  endfacet
  facet normal -0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   2.800000e+01 -1.630000e+01 3.600000e+01
      vertex   2.260000e+01 -1.700000e+01 3.600000e+01
      vertex   1.800000e+00 -1.630000e+01 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   1.800000e+00 -1.630000e+01 3.600000e+01
      vertex   2.260000e+01 -1.700000e+01 3.600000e+01
      vertex   6.100000e+00 -1.700000e+01 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   1.800000e+00 -1.630000e+01 3.600000e+01
      vertex   6.100000e+00 -1.700000e+01 3.600000e+01
      vertex   6.100000e+00 -2.960000e+01 3.600000e+01
    endloop
  endfacet
  facet normal -0.000000e+00 -0.000000e+00 -1.000000e+00
    outer loop
      vertex   3.135000e+01 -3.077545e+01 3.600000e+01
      vertex   4.020000e+01 -4.620000e+01 3.600000e+01
      vertex   2.685000e+01 -3.077545e+01 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 -0.000000e+00 -1.000000e+00
    outer loop
      vertex   2.685000e+01 -3.077545e+01 3.600000e+01
      vertex   4.020000e+01 -4.620000e+01 3.600000e+01
      vertex   -2.000000e-01 -4.620000e+01 3.600000e+01
    endloop
  endfacet
  facet normal -0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   2.685000e+01 -3.077545e+01 3.600000e+01
      vertex   -2.000000e-01 -4.620000e+01 3.600000e+01
      vertex   2.260000e+01 -2.960000e+01 3.600000e+01
    endloop
  endfacet
  facet normal -0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   2.260000e+01 -2.960000e+01 3.600000e+01
      vertex   -2.000000e-01 -4.620000e+01 3.600000e+01
      vertex   6.100000e+00 -2.960000e+01 3.600000e+01
    endloop
  endfacet
  facet normal -0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   6.100000e+00 -2.960000e+01 3.600000e+01
      vertex   -2.000000e-01 -4.620000e+01 3.600000e+01
      vertex   1.800000e+00 -1.630000e+01 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   4.020000e+01 -4.620000e+01 3.600000e+01
      vertex   3.135000e+01 -3.077545e+01 3.600000e+01
      vertex   4.020000e+01 -2.210000e+01 3.600000e+01
    endloop
  endfacet
  facet normal -0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   4.020000e+01 -2.210000e+01 3.600000e+01
      vertex   3.135000e+01 -3.077545e+01 3.600000e+01
      vertex   3.135000e+01 -2.077545e+01 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   -2.000000e-01 -4.620000e+01 3.600000e+01
      vertex   -2.000000e-01 2.000000e-01 3.600000e+01
      vertex   1.800000e+00 -1.630000e+01 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   1.800000e+00 -1.630000e+01 3.600000e+01
      vertex   -2.000000e-01 2.000000e-01 3.600000e+01
      vertex   1.800000e+00 -1.800000e+00 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   1.800000e+00 -1.800000e+00 3.600000e+01
      vertex   -2.000000e-01 2.000000e-01 3.600000e+01
      vertex   2.800000e+01 -1.800000e+00 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   2.800000e+01 -1.800000e+00 3.600000e+01
      vertex   -2.000000e-01 2.000000e-01 3.600000e+01
      vertex   4.020000e+01 2.000000e-01 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   2.800000e+01 -1.800000e+00 3.600000e+01
      vertex   4.020000e+01 2.000000e-01 3.600000e+01
      vertex   4.020000e+01 -1.600000e+00 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   2.800000e+01 -1.630000e+01 3.600000e+01
      vertex   2.800000e+01 -1.800000e+00 3.600000e+01
      vertex   4.020000e+01 -1.600000e+00 3.600000e+01
    endloop
  endfacet
  facet normal 1.000000e+00 -0.000000e+00 0.000000e+00
    outer loop
      vertex   2.800000e+01 -1.630000e+01 3.600000e+01
      vertex   2.800000e+01 -1.411618e+01 3.000000e+01
      vertex   2.800000e+01 -1.800000e+00 3.600000e+01
    endloop
  endfacet
  facet normal 1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   2.800000e+01 -1.800000e+00 3.600000e+01
      vertex   2.800000e+01 -1.411618e+01 3.000000e+01
      vertex   2.800000e+01 -1.800000e+00 3.000000e+01
    endloop
  endfacet
  facet normal -0.000000e+00 -9.396926e-01 -3.420201e-01
    outer loop
      vertex   2.800000e+01 -1.630000e+01 3.600000e+01
      vertex   1.800000e+00 -1.630000e+01 3.600000e+01
      vertex   2.800000e+01 -1.411618e+01 3.000000e+01
    endloop
  endfacet
  facet normal -0.000000e+00 -9.396926e-01 -3.420201e-01
    outer loop
      vertex   2.800000e+01 -1.411618e+01 3.000000e+01
      vertex   1.800000e+00 -1.630000e+01 3.600000e+01
      vertex   1.800000e+00 -1.411618e+01 3.000000e+01
    endloop
  endfacet
  facet normal -0.000000e+00 1.000000e+00 0.000000e+00
    outer loop
      vertex   -2.000000e-01 -4.620000e+01 3.600000e+01
      vertex   4.020000e+01 -4.620000e+01 3.600000e+01
      vertex   -2.000000e-01 -4.620000e+01 3.100000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 1.000000e+00 0.000000e+00
    outer loop
      vertex   -2.000000e-01 -4.620000e+01 3.100000e+01
      vertex   4.020000e+01 -4.620000e+01 3.600000e+01
      vertex   4.020000e+01 -4.620000e+01 3.100000e+01
    endloop
  endfacet
  facet normal 1.000000e+00 9.271798e-17 0.000000e+00
    outer loop
      vertex   -2.000000e-01 2.000000e-01 3.600000e+01
      vertex   -2.000000e-01 -4.620000e+01 3.600000e+01
      vertex   -2.000000e-01 2.000000e-01 3.100000e+01
    endloop
  endfacet
  facet normal 1.000000e+00 9.271798e-17 0.000000e+00
    outer loop
      vertex   -2.000000e-01 2.000000e-01 3.100000e+01
      vertex   -2.000000e-01 -4.620000e+01 3.600000e+01
      vertex   -2.000000e-01 -4.620000e+01 3.100000e+01
    endloop
  endfacet
  facet normal 1.064880e-16 -1.000000e+00 0.000000e+00
    outer loop
      vertex   4.020000e+01 2.000000e-01 3.600000e+01
      vertex   -2.000000e-01 2.000000e-01 3.600000e+01
      vertex   4.020000e+01 2.000000e-01 3.100000e+01
    endloop
  endfacet
  facet normal 1.064880e-16 -1.000000e+00 0.000000e+00
    outer loop
      vertex   4.020000e+01 2.000000e-01 3.100000e+01
      vertex   -2.000000e-01 2.000000e-01 3.600000e+01
      vertex   -2.000000e-01 2.000000e-01 3.100000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 1.000000e+00 -0.000000e+00
    outer loop
      vertex   2.800000e+01 -1.800000e+00 3.000000e+01
      vertex   1.800000e+00 -1.800000e+00 3.000000e+01
      vertex   2.800000e+01 -1.800000e+00 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 1.000000e+00 0.000000e+00
    outer loop
      vertex   2.800000e+01 -1.800000e+00 3.600000e+01
      vertex   1.800000e+00 -1.800000e+00 3.000000e+01
      vertex   1.800000e+00 -1.800000e+00 3.600000e+01
    endloop
  endfacet
  facet normal -1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   1.800000e+00 -1.630000e+01 3.600000e+01
      vertex   1.800000e+00 -1.800000e+00 3.600000e+01
      vertex   1.800000e+00 -1.411618e+01 3.000000e+01
    endloop
  endfacet
  facet normal -1.000000e+00 3.605739e-17 -7.401487e-17
    outer loop
      vertex   1.800000e+00 -1.411618e+01 3.000000e+01
      vertex   1.800000e+00 -1.800000e+00 3.600000e+01
      vertex   1.800000e+00 -1.800000e+00 3.000000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   2.800000e+01 -1.411618e+01 3.000000e+01
      vertex   1.800000e+00 -1.411618e+01 3.000000e+01
      vertex   2.800000e+01 -1.800000e+00 3.000000e+01
    endloop
  endfacet
  facet normal -0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   2.800000e+01 -1.800000e+00 3.000000e+01
      vertex   1.800000e+00 -1.411618e+01 3.000000e+01
      vertex   1.800000e+00 -1.800000e+00 3.000000e+01
    endloop
  endfacet
  facet normal -1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   2.260000e+01 -1.700000e+01 3.600000e+01
      vertex   2.260000e+01 -2.960000e+01 3.600000e+01
      vertex   2.260000e+01 -1.700000e+01 3.760000e+01
    endloop
  endfacet
  facet normal -1.000000e+00 -0.000000e+00 0.000000e+00
    outer loop
      vertex   2.260000e+01 -1.700000e+01 3.760000e+01
      vertex   2.260000e+01 -2.960000e+01 3.600000e+01
      vertex   2.260000e+01 -2.960000e+01 3.760000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 -1.000000e+00 0.000000e+00
    outer loop
      vertex   6.100000e+00 -1.700000e+01 3.600000e+01
      vertex   2.260000e+01 -1.700000e+01 3.600000e+01
      vertex   6.100000e+00 -1.700000e+01 3.760000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 -1.000000e+00 0.000000e+00
    outer loop
      vertex   6.100000e+00 -1.700000e+01 3.760000e+01
      vertex   2.260000e+01 -1.700000e+01 3.600000e+01
      vertex   2.260000e+01 -1.700000e+01 3.760000e+01
    endloop
  endfacet
  facet normal 1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   6.100000e+00 -2.960000e+01 3.600000e+01
      vertex   6.100000e+00 -1.700000e+01 3.600000e+01
      vertex   6.100000e+00 -2.960000e+01 3.760000e+01
    endloop
  endfacet
  facet normal 1.000000e+00 -0.000000e+00 0.000000e+00
    outer loop
      vertex   6.100000e+00 -2.960000e+01 3.760000e+01
      vertex   6.100000e+00 -1.700000e+01 3.600000e+01
      vertex   6.100000e+00 -1.700000e+01 3.760000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 1.000000e+00 -0.000000e+00
    outer loop
      vertex   2.260000e+01 -2.960000e+01 3.600000e+01
      vertex   6.100000e+00 -2.960000e+01 3.600000e+01
      vertex   2.260000e+01 -2.960000e+01 3.760000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 1.000000e+00 0.000000e+00
    outer loop
      vertex   2.260000e+01 -2.960000e+01 3.760000e+01
      vertex   6.100000e+00 -2.960000e+01 3.600000e+01
      vertex   6.100000e+00 -2.960000e+01 3.760000e+01
    endloop
  endfacet
  facet normal 1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   4.170000e+01 -1.600000e+00 3.100000e+01
      vertex   4.170000e+01 1.700000e+00 3.100000e+01
      vertex   4.170000e+01 -1.600000e+00 3.600000e+01
    endloop
  endfacet
  facet normal 1.000000e+00 -0.000000e+00 0.000000e+00
    outer loop
      vertex   4.170000e+01 -1.600000e+00 3.600000e+01
      vertex   4.170000e+01 1.700000e+00 3.100000e+01
      vertex   4.170000e+01 1.700000e+00 3.760000e+01
    endloop
  endfacet
  facet normal 1.000000e+00 0.000000e+00 -0.000000e+00
    outer loop
      vertex   4.170000e+01 -1.600000e+00 3.600000e+01
      vertex   4.170000e+01 1.700000e+00 3.760000e+01
      vertex   4.170000e+01 -2.210000e+01 3.600000e+01
    endloop
  endfacet
  facet normal 1.000000e+00 0.000000e+00 -0.000000e+00
    outer loop
      vertex   4.170000e+01 -2.210000e+01 3.600000e+01
      vertex   4.170000e+01 1.700000e+00 3.760000e+01
      vertex   4.170000e+01 -4.770000e+01 3.760000e+01
    endloop
  endfacet
  facet normal 1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   4.170000e+01 -2.210000e+01 3.600000e+01
      vertex   4.170000e+01 -4.770000e+01 3.760000e+01
      vertex   4.170000e+01 -4.770000e+01 3.100000e+01
    endloop
  endfacet
  facet normal 1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   4.170000e+01 -4.770000e+01 3.100000e+01
      vertex   4.170000e+01 -2.210000e+01 3.100000e+01
      vertex   4.170000e+01 -2.210000e+01 3.600000e+01
    endloop
  endfacet
  facet normal -0.000000e+00 -1.000000e+00 -0.000000e+00
    outer loop
      vertex   4.170000e+01 -4.770000e+01 3.760000e+01
      vertex   -1.700000e+00 -4.770000e+01 3.760000e+01
      vertex   4.170000e+01 -4.770000e+01 3.100000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 -1.000000e+00 0.000000e+00
    outer loop
      vertex   4.170000e+01 -4.770000e+01 3.100000e+01
      vertex   -1.700000e+00 -4.770000e+01 3.760000e+01
      vertex   -1.700000e+00 -4.770000e+01 3.100000e+01
    endloop
  endfacet
  facet normal -1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   -1.700000e+00 -4.770000e+01 3.760000e+01
      vertex   -1.700000e+00 1.700000e+00 3.760000e+01
      vertex   -1.700000e+00 -4.770000e+01 3.100000e+01
    endloop
  endfacet
  facet normal -1.000000e+00 -2.247415e-17 1.682156e-16
    outer loop
      vertex   -1.700000e+00 -4.770000e+01 3.100000e+01
      vertex   -1.700000e+00 1.700000e+00 3.760000e+01
      vertex   -1.700000e+00 1.700000e+00 3.100000e+01
    endloop
  endfacet
  facet normal -0.000000e+00 1.000000e+00 0.000000e+00
    outer loop
      vertex   -1.700000e+00 1.700000e+00 3.760000e+01
      vertex   4.170000e+01 1.700000e+00 3.760000e+01
      vertex   -1.700000e+00 1.700000e+00 3.100000e+01
    endloop
  endfacet
  facet normal -2.046494e-17 1.000000e+00 1.345725e-16
    outer loop
      vertex   -1.700000e+00 1.700000e+00 3.100000e+01
      vertex   4.170000e+01 1.700000e+00 3.760000e+01
      vertex   4.170000e+01 1.700000e+00 3.100000e+01
    endloop
  endfacet
  facet normal -0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   6.100000e+00 -2.960000e+01 3.760000e+01
      vertex   -1.700000e+00 -4.770000e+01 3.760000e+01
      vertex   2.260000e+01 -2.960000e+01 3.760000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   2.260000e+01 -2.960000e+01 3.760000e+01
      vertex   -1.700000e+00 -4.770000e+01 3.760000e+01
      vertex   4.170000e+01 -4.770000e+01 3.760000e+01
    endloop
  endfacet
  facet normal -0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   2.260000e+01 -2.960000e+01 3.760000e+01
      vertex   4.170000e+01 -4.770000e+01 3.760000e+01
      vertex   2.260000e+01 -1.700000e+01 3.760000e+01
    endloop
  endfacet
  facet normal -0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   2.260000e+01 -1.700000e+01 3.760000e+01
      vertex   4.170000e+01 -4.770000e+01 3.760000e+01
      vertex   4.170000e+01 1.700000e+00 3.760000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 -0.000000e+00 1.000000e+00
    outer loop
      vertex   2.260000e+01 -1.700000e+01 3.760000e+01
      vertex   4.170000e+01 1.700000e+00 3.760000e+01
      vertex   -1.700000e+00 1.700000e+00 3.760000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 -0.000000e+00 1.000000e+00
    outer loop
      vertex   6.100000e+00 -2.960000e+01 3.760000e+01
      vertex   6.100000e+00 -1.700000e+01 3.760000e+01
      vertex   -1.700000e+00 -4.770000e+01 3.760000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   -1.700000e+00 -4.770000e+01 3.760000e+01
      vertex   6.100000e+00 -1.700000e+01 3.760000e+01
      vertex   -1.700000e+00 1.700000e+00 3.760000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   -1.700000e+00 1.700000e+00 3.760000e+01
      vertex   6.100000e+00 -1.700000e+01 3.760000e+01
      vertex   2.260000e+01 -1.700000e+01 3.760000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 -1.000000e+00 0.000000e+00
    outer loop
      vertex   3.315000e+01 -3.840000e+01 3.300000e+01
      vertex   3.315000e+01 -3.840000e+01 3.600000e+01
      vertex   3.155000e+01 -3.840000e+01 3.300000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 -1.000000e+00 0.000000e+00
    outer loop
      vertex   3.155000e+01 -3.840000e+01 3.300000e+01
      vertex   3.315000e+01 -3.840000e+01 3.600000e+01
      vertex   3.155000e+01 -3.840000e+01 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   3.315000e+01 -3.840000e+01 3.300000e+01
      vertex   3.155000e+01 -3.840000e+01 3.300000e+01
      vertex   3.315000e+01 -1.600000e+00 3.300000e+01
    endloop
  endfacet
  facet normal -0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   3.315000e+01 -1.600000e+00 3.300000e+01
      vertex   3.155000e+01 -3.840000e+01 3.300000e+01
      vertex   3.155000e+01 -1.600000e+00 3.300000e+01
    endloop
  endfacet
  facet normal -1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   3.155000e+01 -3.840000e+01 3.600000e+01
      vertex   3.155000e+01 -1.600000e+00 3.600000e+01
      vertex   3.155000e+01 -3.840000e+01 3.300000e+01
    endloop
  endfacet
  facet normal -1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   3.155000e+01 -3.840000e+01 3.300000e+01
      vertex   3.155000e+01 -1.600000e+00 3.600000e+01
      vertex   3.155000e+01 -1.600000e+00 3.300000e+01
    endloop
  endfacet
  facet normal 1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   3.315000e+01 -3.840000e+01 3.300000e+01
      vertex   3.315000e+01 -1.600000e+00 3.300000e+01
      vertex   3.315000e+01 -3.840000e+01 3.600000e+01
    endloop
  endfacet
  facet normal 1.000000e+00 -0.000000e+00 0.000000e+00
    outer loop
      vertex   3.315000e+01 -3.840000e+01 3.600000e+01
      vertex   3.315000e+01 -1.600000e+00 3.300000e+01
      vertex   3.315000e+01 -1.600000e+00 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 1.000000e+00 0.000000e+00
    outer loop
      vertex   4.000000e+01 -2.210000e+01 3.600000e+01
      vertex   4.000000e+01 -2.210000e+01 2.050000e+01
      vertex   3.840000e+01 -2.210000e+01 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 1.000000e+00 0.000000e+00
    outer loop
      vertex   3.840000e+01 -2.210000e+01 3.600000e+01
      vertex   4.000000e+01 -2.210000e+01 2.050000e+01
      vertex   3.840000e+01 -2.210000e+01 2.050000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 -1.000000e+00 0.000000e+00
    outer loop
      vertex   0.000000e+00 -4.600000e+01 0.000000e+00
      vertex   7.600000e+00 -4.600000e+01 1.260000e+01
      vertex   0.000000e+00 -4.600000e+01 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 -1.000000e+00 0.000000e+00
    outer loop
      vertex   0.000000e+00 -4.600000e+01 3.600000e+01
      vertex   7.600000e+00 -4.600000e+01 1.260000e+01
      vertex   1.360000e+01 -4.600000e+01 2.060000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 -1.000000e+00 0.000000e+00
    outer loop
      vertex   0.000000e+00 -4.600000e+01 3.600000e+01
      vertex   1.360000e+01 -4.600000e+01 2.060000e+01
      vertex   1.360000e+01 -4.600000e+01 2.760000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 -1.000000e+00 0.000000e+00
    outer loop
      vertex   4.000000e+01 -4.600000e+01 0.000000e+00
      vertex   1.960000e+01 -4.600000e+01 5.600000e+00
      vertex   0.000000e+00 -4.600000e+01 0.000000e+00
    endloop
  endfacet
  facet normal 0.000000e+00 -1.000000e+00 0.000000e+00
    outer loop
      vertex   0.000000e+00 -4.600000e+01 0.000000e+00
      vertex   1.960000e+01 -4.600000e+01 5.600000e+00
      vertex   7.600000e+00 -4.600000e+01 5.600000e+00
    endloop
  endfacet
  facet normal 0.000000e+00 -1.000000e+00 0.000000e+00
    outer loop
      vertex   0.000000e+00 -4.600000e+01 0.000000e+00
      vertex   7.600000e+00 -4.600000e+01 5.600000e+00
      vertex   7.600000e+00 -4.600000e+01 1.260000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 -1.000000e+00 -0.000000e+00
    outer loop
      vertex   4.000000e+01 -4.600000e+01 3.600000e+01
      vertex   2.560000e+01 -4.600000e+01 2.060000e+01
      vertex   4.000000e+01 -4.600000e+01 0.000000e+00
    endloop
  endfacet
  facet normal 0.000000e+00 -1.000000e+00 0.000000e+00
    outer loop
      vertex   4.000000e+01 -4.600000e+01 0.000000e+00
      vertex   2.560000e+01 -4.600000e+01 2.060000e+01
      vertex   1.960000e+01 -4.600000e+01 1.260000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 -1.000000e+00 0.000000e+00
    outer loop
      vertex   4.000000e+01 -4.600000e+01 0.000000e+00
      vertex   1.960000e+01 -4.600000e+01 1.260000e+01
      vertex   1.960000e+01 -4.600000e+01 5.600000e+00
    endloop
  endfacet
  facet normal 0.000000e+00 -1.000000e+00 0.000000e+00
    outer loop
      vertex   2.560000e+01 -4.600000e+01 2.060000e+01
      vertex   4.000000e+01 -4.600000e+01 3.600000e+01
      vertex   2.560000e+01 -4.600000e+01 2.760000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 -1.000000e+00 0.000000e+00
    outer loop
      vertex   2.560000e+01 -4.600000e+01 2.760000e+01
      vertex   4.000000e+01 -4.600000e+01 3.600000e+01
      vertex   0.000000e+00 -4.600000e+01 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 -1.000000e+00 0.000000e+00
    outer loop
      vertex   2.560000e+01 -4.600000e+01 2.760000e+01
      vertex   0.000000e+00 -4.600000e+01 3.600000e+01
      vertex   1.360000e+01 -4.600000e+01 2.760000e+01
    endloop
  endfacet
  facet normal -0.000000e+00 -1.000000e+00 0.000000e+00
    outer loop
      vertex   2.560000e+01 -4.600000e+01 2.060000e+01
      vertex   1.360000e+01 -4.600000e+01 2.060000e+01
      vertex   1.960000e+01 -4.600000e+01 1.260000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 -1.000000e+00 0.000000e+00
    outer loop
      vertex   1.960000e+01 -4.600000e+01 1.260000e+01
      vertex   1.360000e+01 -4.600000e+01 2.060000e+01
      vertex   7.600000e+00 -4.600000e+01 1.260000e+01
    endloop
  endfacet
  facet normal -1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   0.000000e+00 0.000000e+00 0.000000e+00
      vertex   0.000000e+00 -4.600000e+01 0.000000e+00
      vertex   0.000000e+00 0.000000e+00 3.600000e+01
    endloop
  endfacet
  facet normal -1.000000e+00 -0.000000e+00 0.000000e+00
    outer loop
      vertex   0.000000e+00 0.000000e+00 3.600000e+01
      vertex   0.000000e+00 -4.600000e+01 0.000000e+00
      vertex   0.000000e+00 -4.600000e+01 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 1.000000e+00 -0.000000e+00
    outer loop
      vertex   4.000000e+01 0.000000e+00 0.000000e+00
      vertex   0.000000e+00 0.000000e+00 0.000000e+00
      vertex   4.000000e+01 0.000000e+00 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 1.000000e+00 0.000000e+00
    outer loop
      vertex   4.000000e+01 0.000000e+00 3.600000e+01
      vertex   0.000000e+00 0.000000e+00 0.000000e+00
      vertex   0.000000e+00 0.000000e+00 3.600000e+01
    endloop
  endfacet
  facet normal 1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   4.000000e+01 -2.210000e+01 3.600000e+01
      vertex   4.000000e+01 -4.600000e+01 3.600000e+01
      vertex   4.000000e+01 -2.210000e+01 2.050000e+01
    endloop
  endfacet
  facet normal 1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   4.000000e+01 -2.210000e+01 2.050000e+01
      vertex   4.000000e+01 -4.600000e+01 3.600000e+01
      vertex   4.000000e+01 -4.600000e+01 0.000000e+00
    endloop
  endfacet
  facet normal 1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   4.000000e+01 -2.210000e+01 2.050000e+01
      vertex   4.000000e+01 -4.600000e+01 0.000000e+00
      vertex   4.000000e+01 0.000000e+00 0.000000e+00
    endloop
  endfacet
  facet normal 1.000000e+00 -0.000000e+00 0.000000e+00
    outer loop
      vertex   4.000000e+01 -2.210000e+01 2.050000e+01
      vertex   4.000000e+01 0.000000e+00 0.000000e+00
      vertex   4.000000e+01 -1.600000e+00 2.050000e+01
    endloop
  endfacet
  facet normal 1.000000e+00 -0.000000e+00 0.000000e+00
    outer loop
      vertex   4.000000e+01 -1.600000e+00 2.050000e+01
      vertex   4.000000e+01 0.000000e+00 0.000000e+00
      vertex   4.000000e+01 0.000000e+00 3.600000e+01
    endloop
  endfacet
  facet normal 1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   4.000000e+01 -1.600000e+00 2.050000e+01
      vertex   4.000000e+01 0.000000e+00 3.600000e+01
      vertex   4.000000e+01 -1.600000e+00 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   3.840000e+01 -2.210000e+01 2.050000e+01
      vertex   4.000000e+01 -2.210000e+01 2.050000e+01
      vertex   3.840000e+01 -1.600000e+00 2.050000e+01
    endloop
  endfacet
  facet normal -0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   3.840000e+01 -1.600000e+00 2.050000e+01
      vertex   4.000000e+01 -2.210000e+01 2.050000e+01
      vertex   4.000000e+01 -1.600000e+00 2.050000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   3.155000e+01 -3.840000e+01 3.600000e+01
      vertex   3.315000e+01 -3.840000e+01 3.600000e+01
      vertex   3.155000e+01 -1.600000e+00 3.600000e+01
    endloop
  endfacet
  facet normal -0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   3.155000e+01 -1.600000e+00 3.600000e+01
      vertex   3.315000e+01 -3.840000e+01 3.600000e+01
      vertex   3.315000e+01 -1.600000e+00 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   3.155000e+01 -1.600000e+00 3.600000e+01
      vertex   3.315000e+01 -1.600000e+00 3.600000e+01
      vertex   4.000000e+01 0.000000e+00 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   4.000000e+01 0.000000e+00 3.600000e+01
      vertex   3.315000e+01 -1.600000e+00 3.600000e+01
      vertex   4.000000e+01 -1.600000e+00 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   4.000000e+01 0.000000e+00 3.600000e+01
      vertex   0.000000e+00 0.000000e+00 3.600000e+01
      vertex   3.155000e+01 -1.600000e+00 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   3.155000e+01 -1.600000e+00 3.600000e+01
      vertex   0.000000e+00 0.000000e+00 3.600000e+01
      vertex   1.600000e+00 -1.600000e+00 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   1.600000e+00 -1.600000e+00 3.600000e+01
      vertex   0.000000e+00 0.000000e+00 3.600000e+01
      vertex   0.000000e+00 -4.600000e+01 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   1.600000e+00 -1.600000e+00 3.600000e+01
      vertex   0.000000e+00 -4.600000e+01 3.600000e+01
      vertex   1.600000e+00 -4.440000e+01 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   1.600000e+00 -4.440000e+01 3.600000e+01
      vertex   0.000000e+00 -4.600000e+01 3.600000e+01
      vertex   4.000000e+01 -4.600000e+01 3.600000e+01
    endloop
  endfacet
  facet normal -0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   1.600000e+00 -4.440000e+01 3.600000e+01
      vertex   4.000000e+01 -4.600000e+01 3.600000e+01
      vertex   3.840000e+01 -4.440000e+01 3.600000e+01
    endloop
  endfacet
  facet normal -0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   3.840000e+01 -4.440000e+01 3.600000e+01
      vertex   4.000000e+01 -4.600000e+01 3.600000e+01
      vertex   4.000000e+01 -2.210000e+01 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   3.840000e+01 -4.440000e+01 3.600000e+01
      vertex   4.000000e+01 -2.210000e+01 3.600000e+01
      vertex   3.840000e+01 -2.210000e+01 3.600000e+01
    endloop
  endfacet
  facet normal -1.000000e+00 -0.000000e+00 -0.000000e+00
    outer loop
      vertex   3.840000e+01 -2.210000e+01 3.600000e+01
      vertex   3.840000e+01 -2.210000e+01 2.050000e+01
      vertex   3.840000e+01 -4.440000e+01 3.600000e+01
    endloop
  endfacet
  facet normal -1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   3.840000e+01 -4.440000e+01 3.600000e+01
      vertex   3.840000e+01 -2.210000e+01 2.050000e+01
      vertex   3.840000e+01 -4.440000e+01 1.600000e+00
    endloop
  endfacet
  facet normal -1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   3.840000e+01 -4.440000e+01 1.600000e+00
      vertex   3.840000e+01 -2.210000e+01 2.050000e+01
      vertex   3.840000e+01 -1.600000e+00 1.600000e+00
    endloop
  endfacet
  facet normal -1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   3.840000e+01 -1.600000e+00 1.600000e+00
      vertex   3.840000e+01 -2.210000e+01 2.050000e+01
      vertex   3.840000e+01 -1.600000e+00 2.050000e+01
    endloop
  endfacet
  facet normal 1.000000e+00 0.000000e+00 -0.000000e+00
    outer loop
      vertex   7.600000e+00 -4.440000e+01 5.600000e+00
      vertex   7.600000e+00 -4.440000e+01 1.260000e+01
      vertex   7.600000e+00 -4.600000e+01 5.600000e+00
    endloop
  endfacet
  facet normal 1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   7.600000e+00 -4.600000e+01 5.600000e+00
      vertex   7.600000e+00 -4.440000e+01 1.260000e+01
      vertex   7.600000e+00 -4.600000e+01 1.260000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   1.960000e+01 -4.440000e+01 5.600000e+00
      vertex   7.600000e+00 -4.440000e+01 5.600000e+00
      vertex   1.960000e+01 -4.600000e+01 5.600000e+00
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   1.960000e+01 -4.600000e+01 5.600000e+00
      vertex   7.600000e+00 -4.440000e+01 5.600000e+00
      vertex   7.600000e+00 -4.600000e+01 5.600000e+00
    endloop
  endfacet
  facet normal -1.000000e+00 -0.000000e+00 -0.000000e+00
    outer loop
      vertex   1.960000e+01 -4.440000e+01 1.260000e+01
      vertex   1.960000e+01 -4.440000e+01 5.600000e+00
      vertex   1.960000e+01 -4.600000e+01 1.260000e+01
    endloop
  endfacet
  facet normal -1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   1.960000e+01 -4.600000e+01 1.260000e+01
      vertex   1.960000e+01 -4.440000e+01 5.600000e+00
      vertex   1.960000e+01 -4.600000e+01 5.600000e+00
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   7.600000e+00 -4.440000e+01 1.260000e+01
      vertex   1.960000e+01 -4.440000e+01 1.260000e+01
      vertex   7.600000e+00 -4.600000e+01 1.260000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   7.600000e+00 -4.600000e+01 1.260000e+01
      vertex   1.960000e+01 -4.440000e+01 1.260000e+01
      vertex   1.960000e+01 -4.600000e+01 1.260000e+01
    endloop
  endfacet
  facet normal 1.000000e+00 0.000000e+00 -0.000000e+00
    outer loop
      vertex   1.360000e+01 -4.440000e+01 2.060000e+01
      vertex   1.360000e+01 -4.440000e+01 2.760000e+01
      vertex   1.360000e+01 -4.600000e+01 2.060000e+01
    endloop
  endfacet
  facet normal 1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   1.360000e+01 -4.600000e+01 2.060000e+01
      vertex   1.360000e+01 -4.440000e+01 2.760000e+01
      vertex   1.360000e+01 -4.600000e+01 2.760000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   2.560000e+01 -4.440000e+01 2.060000e+01
      vertex   1.360000e+01 -4.440000e+01 2.060000e+01
      vertex   2.560000e+01 -4.600000e+01 2.060000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   2.560000e+01 -4.600000e+01 2.060000e+01
      vertex   1.360000e+01 -4.440000e+01 2.060000e+01
      vertex   1.360000e+01 -4.600000e+01 2.060000e+01
    endloop
  endfacet
  facet normal -1.000000e+00 -0.000000e+00 -0.000000e+00
    outer loop
      vertex   2.560000e+01 -4.440000e+01 2.760000e+01
      vertex   2.560000e+01 -4.440000e+01 2.060000e+01
      vertex   2.560000e+01 -4.600000e+01 2.760000e+01
    endloop
  endfacet
  facet normal -1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   2.560000e+01 -4.600000e+01 2.760000e+01
      vertex   2.560000e+01 -4.440000e+01 2.060000e+01
      vertex   2.560000e+01 -4.600000e+01 2.060000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   1.360000e+01 -4.440000e+01 2.760000e+01
      vertex   2.560000e+01 -4.440000e+01 2.760000e+01
      vertex   1.360000e+01 -4.600000e+01 2.760000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   1.360000e+01 -4.600000e+01 2.760000e+01
      vertex   2.560000e+01 -4.440000e+01 2.760000e+01
      vertex   2.560000e+01 -4.600000e+01 2.760000e+01
    endloop
  endfacet
  facet normal 1.000000e+00 -1.037592e-17 0.000000e+00
    outer loop
      vertex   1.600000e+00 -4.440000e+01 1.600000e+00
      vertex   1.600000e+00 -1.600000e+00 1.600000e+00
      vertex   1.600000e+00 -4.440000e+01 3.600000e+01
    endloop
  endfacet
  facet normal 1.000000e+00 -1.037592e-17 0.000000e+00
    outer loop
      vertex   1.600000e+00 -4.440000e+01 3.600000e+01
      vertex   1.600000e+00 -1.600000e+00 1.600000e+00
      vertex   1.600000e+00 -1.600000e+00 3.600000e+01
    endloop
  endfacet
  facet normal 9.313225e-10 -1.000000e+00 0.000000e+00
    outer loop
      vertex   3.155000e+01 -1.600000e+00 3.600000e+01
      vertex   1.600000e+00 -1.600000e+00 3.600000e+01
      vertex   3.155000e+01 -1.600000e+00 3.300000e+01
    endloop
  endfacet
  facet normal 9.313225e-10 -1.000000e+00 0.000000e+00
    outer loop
      vertex   3.155000e+01 -1.600000e+00 3.300000e+01
      vertex   1.600000e+00 -1.600000e+00 3.600000e+01
      vertex   1.600000e+00 -1.600000e+00 1.600000e+00
    endloop
  endfacet
  facet normal -8.943360e-10 -1.000000e+00 1.741353e-09
    outer loop
      vertex   3.155000e+01 -1.600000e+00 3.300000e+01
      vertex   1.600000e+00 -1.600000e+00 1.600000e+00
      vertex   3.840000e+01 -1.600000e+00 2.050000e+01
    endloop
  endfacet
  facet normal -1.206764e-17 -1.000000e+00 -2.349678e-17
    outer loop
      vertex   3.840000e+01 -1.600000e+00 2.050000e+01
      vertex   1.600000e+00 -1.600000e+00 1.600000e+00
      vertex   3.840000e+01 -1.600000e+00 1.600000e+00
    endloop
  endfacet
  facet normal 0.000000e+00 -1.000000e+00 2.231449e-09
    outer loop
      vertex   3.155000e+01 -1.600000e+00 3.300000e+01
      vertex   3.840000e+01 -1.600000e+00 2.050000e+01
      vertex   3.315000e+01 -1.600000e+00 3.300000e+01
    endloop
  endfacet
  facet normal 2.235174e-08 -1.000000e+00 1.161918e-08
    outer loop
      vertex   3.315000e+01 -1.600000e+00 3.300000e+01
      vertex   3.840000e+01 -1.600000e+00 2.050000e+01
      vertex   4.000000e+01 -1.600000e+00 2.050000e+01
    endloop
  endfacet
  facet normal 1.148858e-09 -1.000000e+00 0.000000e+00
    outer loop
      vertex   3.315000e+01 -1.600000e+00 3.300000e+01
      vertex   4.000000e+01 -1.600000e+00 2.050000e+01
      vertex   4.000000e+01 -1.600000e+00 3.600000e+01
    endloop
  endfacet
  facet normal 1.148858e-09 -1.000000e+00 7.401487e-16
    outer loop
      vertex   4.000000e+01 -1.600000e+00 3.600000e+01
      vertex   3.315000e+01 -1.600000e+00 3.600000e+01
      vertex   3.315000e+01 -1.600000e+00 3.300000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 1.000000e+00 -1.691768e-15
    outer loop
      vertex   3.840000e+01 -4.440000e+01 3.600000e+01
      vertex   2.560000e+01 -4.440000e+01 2.760000e+01
      vertex   1.600000e+00 -4.440000e+01 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 1.000000e+00 -1.691768e-15
    outer loop
      vertex   1.600000e+00 -4.440000e+01 3.600000e+01
      vertex   2.560000e+01 -4.440000e+01 2.760000e+01
      vertex   1.360000e+01 -4.440000e+01 2.760000e+01
    endloop
  endfacet
  facet normal 1.184238e-15 1.000000e+00 0.000000e+00
    outer loop
      vertex   1.600000e+00 -4.440000e+01 3.600000e+01
      vertex   1.360000e+01 -4.440000e+01 2.760000e+01
      vertex   1.360000e+01 -4.440000e+01 2.060000e+01
    endloop
  endfacet
  facet normal -1.110223e-15 1.000000e+00 0.000000e+00
    outer loop
      vertex   2.560000e+01 -4.440000e+01 2.760000e+01
      vertex   3.840000e+01 -4.440000e+01 3.600000e+01
      vertex   2.560000e+01 -4.440000e+01 2.060000e+01
    endloop
  endfacet
  facet normal -1.110223e-15 1.000000e+00 0.000000e+00
    outer loop
      vertex   2.560000e+01 -4.440000e+01 2.060000e+01
      vertex   3.840000e+01 -4.440000e+01 3.600000e+01
      vertex   3.840000e+01 -4.440000e+01 1.600000e+00
    endloop
  endfacet
  facet normal -5.253551e-16 1.000000e+00 3.940163e-16
    outer loop
      vertex   2.560000e+01 -4.440000e+01 2.060000e+01
      vertex   3.840000e+01 -4.440000e+01 1.600000e+00
      vertex   1.960000e+01 -4.440000e+01 1.260000e+01
    endloop
  endfacet
  facet normal -7.558965e-16 1.000000e+00 0.000000e+00
    outer loop
      vertex   1.960000e+01 -4.440000e+01 1.260000e+01
      vertex   3.840000e+01 -4.440000e+01 1.600000e+00
      vertex   1.960000e+01 -4.440000e+01 5.600000e+00
    endloop
  endfacet
  facet normal 0.000000e+00 1.000000e+00 3.552714e-15
    outer loop
      vertex   1.960000e+01 -4.440000e+01 5.600000e+00
      vertex   3.840000e+01 -4.440000e+01 1.600000e+00
      vertex   1.600000e+00 -4.440000e+01 1.600000e+00
    endloop
  endfacet
  facet normal 0.000000e+00 1.000000e+00 3.552714e-15
    outer loop
      vertex   1.960000e+01 -4.440000e+01 5.600000e+00
      vertex   1.600000e+00 -4.440000e+01 1.600000e+00
      vertex   7.600000e+00 -4.440000e+01 5.600000e+00
    endloop
  endfacet
  facet normal 2.368476e-15 1.000000e+00 -0.000000e+00
    outer loop
      vertex   7.600000e+00 -4.440000e+01 5.600000e+00
      vertex   1.600000e+00 -4.440000e+01 1.600000e+00
      vertex   7.600000e+00 -4.440000e+01 1.260000e+01
    endloop
  endfacet
  facet normal 2.368476e-15 1.000000e+00 0.000000e+00
    outer loop
      vertex   7.600000e+00 -4.440000e+01 1.260000e+01
      vertex   1.600000e+00 -4.440000e+01 1.600000e+00
      vertex   1.600000e+00 -4.440000e+01 3.600000e+01
    endloop
  endfacet
  facet normal 6.034333e-16 1.000000e+00 -4.525750e-16
    outer loop
      vertex   7.600000e+00 -4.440000e+01 1.260000e+01
      vertex   1.600000e+00 -4.440000e+01 3.600000e+01
      vertex   1.360000e+01 -4.440000e+01 2.060000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 1.000000e+00 0.000000e+00
    outer loop
      vertex   2.560000e+01 -4.440000e+01 2.060000e+01
      vertex   1.960000e+01 -4.440000e+01 1.260000e+01
      vertex   1.360000e+01 -4.440000e+01 2.060000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 1.000000e+00 0.000000e+00
    outer loop
      vertex   1.360000e+01 -4.440000e+01 2.060000e+01
      vertex   1.960000e+01 -4.440000e+01 1.260000e+01
      vertex   7.600000e+00 -4.440000e+01 1.260000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   1.600000e+00 -4.440000e+01 1.600000e+00
      vertex   3.840000e+01 -4.440000e+01 1.600000e+00
      vertex   1.600000e+00 -1.600000e+00 1.600000e+00
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   1.600000e+00 -1.600000e+00 1.600000e+00
      vertex   3.840000e+01 -4.440000e+01 1.600000e+00
      vertex   3.840000e+01 -1.600000e+00 1.600000e+00
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   4.000000e+01 -4.600000e+01 0.000000e+00
      vertex   0.000000e+00 -4.600000e+01 0.000000e+00
      vertex   4.000000e+01 0.000000e+00 0.000000e+00
    endloop
  endfacet
  facet normal -0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   4.000000e+01 0.000000e+00 0.000000e+00
      vertex   0.000000e+00 -4.600000e+01 0.000000e+00
      vertex   0.000000e+00 0.000000e+00 0.000000e+00
    endloop
  endfacet
  facet normal 0.000000e+00 -0.000000e+00 1.000000e+00
    outer loop
      vertex   3.315000e+01 -4.440000e+01 3.000000e+01
      vertex   3.315000e+01 -3.840000e+01 3.000000e+01
      vertex   3.155000e+01 -4.440000e+01 3.000000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   3.155000e+01 -4.440000e+01 3.000000e+01
      vertex   3.315000e+01 -3.840000e+01 3.000000e+01
      vertex   3.155000e+01 -3.840000e+01 3.000000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 -1.000000e+00 0.000000e+00
    outer loop
      vertex   3.315000e+01 -3.840000e+01 3.000000e+01
      vertex   3.315000e+01 -3.840000e+01 3.600000e+01
      vertex   3.155000e+01 -3.840000e+01 3.000000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 -1.000000e+00 0.000000e+00
    outer loop
      vertex   3.155000e+01 -3.840000e+01 3.000000e+01
      vertex   3.315000e+01 -3.840000e+01 3.600000e+01
      vertex   3.155000e+01 -3.840000e+01 3.600000e+01
    endloop
  endfacet
  facet normal -0.000000e+00 -1.000000e+00 -0.000000e+00
    outer loop
      vertex   3.315000e+01 -4.440000e+01 3.000000e+01
      vertex   3.155000e+01 -4.440000e+01 3.000000e+01
      vertex   3.315000e+01 -4.440000e+01 2.150000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 -1.000000e+00 0.000000e+00
    outer loop
      vertex   3.315000e+01 -4.440000e+01 2.150000e+01
      vertex   3.155000e+01 -4.440000e+01 3.000000e+01
      vertex   3.155000e+01 -4.440000e+01 2.150000e+01
    endloop
  endfacet
  facet normal -1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   3.155000e+01 -4.440000e+01 3.000000e+01
      vertex   3.155000e+01 -3.840000e+01 3.000000e+01
      vertex   3.155000e+01 -4.440000e+01 2.150000e+01
    endloop
  endfacet
  facet normal -1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   3.155000e+01 -4.440000e+01 2.150000e+01
      vertex   3.155000e+01 -3.840000e+01 3.000000e+01
      vertex   3.155000e+01 -1.600000e+00 2.150000e+01
    endloop
  endfacet
  facet normal -1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   3.155000e+01 -1.600000e+00 2.150000e+01
      vertex   3.155000e+01 -3.840000e+01 3.000000e+01
      vertex   3.155000e+01 -1.600000e+00 3.600000e+01
    endloop
  endfacet
  facet normal -1.000000e+00 -0.000000e+00 0.000000e+00
    outer loop
      vertex   3.155000e+01 -1.600000e+00 3.600000e+01
      vertex   3.155000e+01 -3.840000e+01 3.000000e+01
      vertex   3.155000e+01 -3.840000e+01 3.600000e+01
    endloop
  endfacet
  facet normal 1.000000e+00 -0.000000e+00 0.000000e+00
    outer loop
      vertex   3.315000e+01 -4.440000e+01 3.000000e+01
      vertex   3.315000e+01 -4.440000e+01 2.150000e+01
      vertex   3.315000e+01 -3.840000e+01 3.000000e+01
    endloop
  endfacet
  facet normal 1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   3.315000e+01 -3.840000e+01 3.000000e+01
      vertex   3.315000e+01 -4.440000e+01 2.150000e+01
      vertex   3.315000e+01 -1.600000e+00 2.150000e+01
    endloop
  endfacet
  facet normal 1.000000e+00 -0.000000e+00 0.000000e+00
    outer loop
      vertex   3.315000e+01 -3.840000e+01 3.000000e+01
      vertex   3.315000e+01 -1.600000e+00 2.150000e+01
      vertex   3.315000e+01 -1.600000e+00 3.600000e+01
    endloop
  endfacet
  facet normal 1.000000e+00 0.000000e+00 0.000000e+00
    outer loop
      vertex   3.315000e+01 -1.600000e+00 3.600000e+01
      vertex   3.315000e+01 -3.840000e+01 3.600000e+01
      vertex   3.315000e+01 -3.840000e+01 3.000000e+01
    endloop
  endfacet
  facet normal -1.387779e-15 1.000000e+00 0.000000e+00
    outer loop
      vertex   3.155000e+01 -1.600000e+00 3.600000e+01
      vertex   3.315000e+01 -1.600000e+00 3.600000e+01
      vertex   3.155000e+01 -1.600000e+00 2.150000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 1.000000e+00 -1.531342e-16
    outer loop
      vertex   3.155000e+01 -1.600000e+00 2.150000e+01
      vertex   3.315000e+01 -1.600000e+00 3.600000e+01
      vertex   3.315000e+01 -1.600000e+00 2.150000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   3.155000e+01 -3.840000e+01 3.600000e+01
      vertex   3.315000e+01 -3.840000e+01 3.600000e+01
      vertex   3.155000e+01 -1.600000e+00 3.600000e+01
    endloop
  endfacet
  facet normal -0.000000e+00 0.000000e+00 1.000000e+00
    outer loop
      vertex   3.155000e+01 -1.600000e+00 3.600000e+01
      vertex   3.315000e+01 -3.840000e+01 3.600000e+01
      vertex   3.315000e+01 -1.600000e+00 3.600000e+01
    endloop
  endfacet
  facet normal 0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   3.315000e+01 -4.440000e+01 2.150000e+01
      vertex   3.155000e+01 -4.440000e+01 2.150000e+01
      vertex   3.315000e+01 -1.600000e+00 2.150000e+01
    endloop
  endfacet
  facet normal -0.000000e+00 0.000000e+00 -1.000000e+00
    outer loop
      vertex   3.315000e+01 -1.600000e+00 2.150000e+01
      vertex   3.155000e+01 -4.440000e+01 2.150000e+01
      vertex   3.155000e+01 -1.600000e+00 2.150000e+01
    endloop
  endfacet
endsolid
```

## Useful links: 
https://tasmota.github.io/docs/AM2301/

https://tasmota.github.io/docs/Rules/

https://tasmota.github.io/docs/Displays/

https://templates.blakadder.com/oled.html

https://iotspace.dev/wemos-d1-mini-battery-shield/
