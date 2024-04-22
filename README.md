_A very hot bedslinger, once a Creality CR-10 V2_

## Current Specifications

### Temperatures:
- **Hotend:** 500°C max
- **Bed:** 240°C max (tested)
- **Build chamber:** 150°C max (135°C nominal, component limitation)
- **Part Cooling, Actively Heated:**  200°C max
- **Linear Guides:** 150°C max
- **Belts:** 135°C continous, 150°C reduced life

### Capabilities:
- **Build Volume:** 310 mm x 310 mm x 200 mm Z (software limited Z)
- **Acceleration:** 2500 mm/s<sup>2</sup>
- **Feedstocks:** 1.75mm PEKK-A, PESU, PPSU, PSU, PEI, PPS, ASA, PA, PC, and more...

### Machine Construction
- **Structure:** All metal frame, no plastic parts
- **Motion System:** Misumi SSELBT16 linear guides, Krytox GPL 225 grease
- **Motors:** LDO Class H Steppers

### Chamber Build
- **Wall construction (inner to outer)**
  - Brushed aluminum sheet, 0.020"
  - Spaceloft Aerogel/PET matting, 6mm
  - PIR foil-faced foam. two layers, 1" thk each, labyrinthine joints
  - Silicone joint adhesive, Permatex RED Optimum
  - Polyimide tape as needed

### Thermal Management
- **Hotend**
  - [Chube](https://chubehotend.com/), 1.75mm air cooled, 42 mm meltzone
  - 0.4 mm nozzle, tungsten carbide, special internal geometry (Brumpbo Tungus design)
  - 24 VDC, 100 W heater cartridge
  - PT1000 temperature sensor (Slice Engineering)
  - Custom "Dab" air manifold, ambient cooling air
  - 24 VDC, 30 W Berd air cooling pump
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



Currently working with a Danger Klipper module for heated part cooling control that will allow both fan speed and the heater core temp to be changed independently.


https://gist.github.com/rogerlz/03ae2b7530cb7587cf652ae4de88a4ae?permalink_comment_id=5031449#gistcomment-5031449

