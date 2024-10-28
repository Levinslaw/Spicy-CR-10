_A $1000 printer doing what a $100,000 printer should do.
Once a Creality CR-10 V2_

## Current Specifications

### Temperatures:
- **Hotend:** 500°C max
- **Bed:** 250°C max (tested)
- **Build chamber:** 150°C max (135°C nominal, component limitation)
- **Part Cooling, Actively Heated:**  270°C max
- **Linear Guides:** 150°C max
- **Belts:** 135°C continous, 150°C with reduced service life

### Capabilities:
- **Build Volume:** 310 mm x 310 mm x 200 mm Z (software limited Z)
- **Acceleration:** 2500 mm/s<sup>2</sup>
- **Feedstocks:** 1.75mm PEKK-A, PESU, PPSU, PSU, PEI, PPS, ASA, PA, PC, and more...

### Machine Construction
- **Structure:** All metal frame, no plastic parts
- **Motion System:** Misumi SSELBT16 linear guides, Krytox GPL 225 grease
- **Motors:** LDO Class H Steppers
- **Wiring:** M22759/32 Spec-55 Raychem Mini-seal splices, no connectors in chamber
- **Pathways:** Raychem DR-25 or PEEK/PPS sheath, SCL or FEP heat shrink tubing
- **Probing:** Beacon, liquid cooled,high-temp cable ~~Cable-driven high temp Z probe stop~~ sensorless homing X/Y
- **Extruder:** Sherpa Micro, ceramic ball bearings, metal gears

### Chamber Build
- **Wall construction (inner to outer)**
  - Brushed aluminum sheet, 0.020"
  - Spaceloft Aerogel/PET matting, 6mm
  - PIR foil-faced foam. two layers, 1" thk each, labyrinthine joints
  - Silicone joint adhesive, Permatex RED Optimum
  - Polyimide tape as needed

### Thermal Management
- **Hotend**
  - [Chube](https://chubehotend.com/), 1.75mm ~~air~~ conduction cooled, ~~42~~ 52 mm meltzone
  - Liquid cooled toolhead carriage
  - 0.4 mm nozzle, tungsten carbide, special internal geometry (Brumpbo Tungus design)
  - 24 VDC, 100 W heater cartridge
  - PT1000 temperature sensor (Slice Engineering)
  - ~~Custom "Dab" air manifold, ambient cooling air~~
  - ~~24 VDC, 30 W Berd air cooling pump~~
- **Bed Heater**  
  - 120 VAC 750W silicone/fiberglass heater pad
  - 6mm THK MIC-6 cast aluminum bed
  - PT1000 temperature sensor (Slice Engineering)
- **Chamber heater**
  - 120 VAC PTCs x2, 600W each
  - 12 VDC, 50W impeller fan, externally mounted, 2820 RPM, XD-3420, perm magnet
  - 12 VDC cooling fan for impeller fan, Noctua 80mm NF-A8
  - PT1000 3-wire, MAX31865 ADC, GPIO on RaspberryPi, free air in chamber
- **Part Cooling Heater**
  - 48 VDC, 150W heater core, taken from 120 VAC hot air rework station
  - Toolhead-mounted part cooling duct
  - PT1000 temperature sensor (Slice Engineering)
  - 24 VDC brushless air pump, high temperature, 3-wire

<details>

<summary>Work In Progress</summary>


- Working with/on a Danger Klipper module for heated part cooling control that allows both fan speed and the heater core temp to be changed independently. It is working well.


- The BTT SKR1.4T has run out of I/O and needs to be replaced by an Octopus with 48VDC stepper drivers. An old PC tower case provides plenty of room for the MCU and associated power supplies and distribution.


- Rebuilding the X-axis gantry to have dual steppers instead of one stepper and an idler. Gantry beams to be laser cut plate aluminum.


- Rebuilding the Z-axis with Wobblex lead screw nuts. Flipping the steppers from bottom drive to top-drive with thrust bearings at the bottom. A pair of bellows shaft couplings will reduce lead screw alignment tolerance.


- Y-axis redesign to include kinematic, three-point coupling for the new magnetic bed. Larger linear guides support the bed carriage in three places. A 120 VAC silicone heater is planned, but may be replaced by mica heaters so the bed can operate above 250C for extreme materials like Extem TPI. The single stepper will be replaced by two stepper motors.


- Extruder and hotend water-cooling is required. Adding water-cooling for the stepper motors will enable 150C continuous chamber operating temperature.


- Active chamber cooling is required to offset the difference between the lowest rated component and the upper limit of heating power of the heaters versus chamber insulation. A small tube and fin automotive intercooler with appropriate fans and ducting will provide air-to-air rejection of the surplus heat.


- Power consumption is high (13-14 amps on a 15 amp wall outlet) despite excellent insulation. Reducing power consumption is vital for safety and economy.


- Better intrinsic safety is desired. Power-enable relays controlled by the host (Raspberry Pi) will enable remote shutdown when thermal runaway is detected and can't be overcome (N/O solid state relays in a failed-closed scenario). Power-up/down workflows will save energy. Dual temperature sensors with comparative capabilities and diverse pathways should be used on heat sources that are not thermally fused nor controlled by solid state relays.


- Filament drying, handling, and feeding needs improvement. Currently the reel is inside the chamber, which provides heating and drying while running. It mounts to a spool holder with a filament guide hoop. Filament is pulled from the reel by the extruder which limits Z travel. At upper end Z heights the filament path becomes short and abrupt. Very brittle filaments can break mid-print. There is no filament runout detection at this time. Heat is lost opening the upper door to load filament and can cause burns to the operator. A filament heating and drying chamber above the printer is needed. 


</details>
