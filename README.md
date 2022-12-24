# humidity-sensor
Tasmota portable humidity sensor with display 


## Rules

### Show sensor readings
```
rule1 on tele-AM2301#Temperature do DisplayText [C0B1s1x36y18]%value%~20~20~20[C0B1s1x69y20k1][C0B1s1x71y18]C endon
      on tele-AM2301#Humidity do DisplayText [C0B1s1x36y32]%value% %~20~20~20 endon
      on tele-AM2301#Humidity do DisplayText [C0B1s1x36y50tS]~20~20 endon
```      
      
### Clear display on boot and show logo
```
rule2 on System#Boot do displaytext [zC0B1zs1x36y18]Hygra[s1x36y32]~20~20~20sense [s1x58y50]v.1.0 endon      
```

### Set rule 1 on 
```
rule1 1
```

### Set rule 2 on 
```
rule2 1
```
