![Voron 2.4 - 1631](/img/Voron2.4.jpg)

# Configuration of Voron 2.4 (2.1631) - 300mm
Electronics:
- Spider v1 + TMC2209
- BTT smart filament sensor

Hardware:
- MGN12H
- GE5C
- [Nevermore Micro V5: carbon air filter](https://github.com/nevermore3d/Nevermore_Micro)
- [AfterBurner(BN v30)](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/Badnoob/AB-BN)

Mods: 
- [Decontaminator and purge bucket](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/edwardyeeks/Decontaminator_Purge_Bucket_&_Nozzle_Scrubber)
- [klicky probe with auto-z calibrate](https://github.com/jlas1/Klicky-Probe/)
- drop first result


# Software
## Drop First Result
I've added this tweak to my configs because the first probing was always off (~-.06) and subsequent ones were ok. 

```
cd ~/klipper  
git remote add skip-first-probe https://github.com/ViThreeDimension/drop-first-result-klipper.git  
git fetch skip-first-probe
sudo service klipper stop
git cherry-pick 75beccd22a70b49b50ae20391b5c0054113eb7b7
sudo service klipper start
```

Then add ```drop_first_result: true``` to `[probe]` section

## Auto-Z calibrate
https://github.com/protoloft/klipper_z_calibration

## Purge bucket
Configuration can be found in [Decontaminator and purge bucket](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/edwardyeeks/Decontaminator_Purge_Bucket_&_Nozzle_Scrubber)

## Adaptive Bed Mesh
Purpose is to mesh only the Area necessary to print.
Source can be found in Frix Repo : [Adaptive Bed Mesh](https://github.com/Frix-x/klipper-voron-V2/blob/main/macros/probing/bed_mesh.cfg)


