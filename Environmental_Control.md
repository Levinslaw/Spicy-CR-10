# Environmental control strategies

Process parameter control is everything in additive manufacturing wherein anisotropic properties are intrinsic to the technology. The environmental controls constitute everything between the toolhead's nozzle and the part build surface.

This machine is a bed slinger in a box design. The enclosure is highly insulated and actively heated. With high performance polymers the insulation is too effective. Measures to actively remove heat from the build volume are needed to maintain the target air temperature and stay under machine design limits.

## Current Configuration

As detailed in the Ethos of High Temperature Additive Manufacturing there are fundamental material and technology limitations afflicting FDM/FFF machine design, especially when the motion system occupies the build volume (from an environmental standpoint). The highest performing commercial machines separate the two. Unless this separation is provided there are practically insurmountable limits in the ~150 C range.

The maximum sustainable chamber temperature is currently 135 C. The Spicy CR-10 has related machine and enclosure limitations as follows:

- Mechanical - static
    - Frame thermal expansion
    - Frame bi-metallic thermal expansion
    - Build plate heater
- Mechanical - dynamic
    - Drive Belts
    - Ball bearings
    - Lubrication
    - Springs
- Thermal
    - Heatbreak
    - Extruder
- Electrical
    - Fan and stepper motor windings
    - Wire
    - Connectors
    - Sensors
- Logistical
    - First layer access
    - Build surface fixturing
    - Material handling and feeding

The present limiting factors in order of lowest continuous use temperature are:
- Stepper motor bearings and coils = 135 C practical
- Drive belts = 135 C continuous
- Heatbreak air cooling = 150 C
- Bimetallic thermal expansion = 150 C?

## Areas of Development

### Chamber cooler

To prevent chamber temperature creep, the chamber door must be propped open slightly. This allows hot/dry chmaber air to escape, and cool/moist air to enter the chamber. While it attenuates temperature this is undesireable for health reasons as fumes and particulate matter are always generated and should be contained.

Introducing unheated, moist air may contaminate extremely hygroscopic filaments. In extreme cases such moisture infiltration can be seen in the over-extruded lines on a printed part.

When the build plate temperature exceeds 150 C the ability of the enclosure to dissipate heat is exceeded and the temperature will climb past the desired set point (nominally 135 C). If build surface temperature needs to be much higher, the enclosure/chamber temperature can creep rapidly and aggressively. The 310 mm x 310 mm aluminum build plate is simply an awesome radiating heater.

The introduction of heated part cooling air up to 260 C exacerbates the issue.

Even though the silicone build surface heater can approach 240 C, the other design limits compel a means to remove the excess heat generated in the course of maintaining bed adhesion and cooling extremely hot molten plastic (but not too much).

The obvious choice is a heat exchanger. It would be preferable to use a liquid-to-air exchanger, but without an existing liquid cooling system an air-ti-air exchanger would be faster to implement.

A small tube-and-fin intercooler from a turbocharged vehicle was selected to be the exchanger. A vendor on Ali-Express provided a Renault R intercooler with the specifications:
   - Core Size: W 204 mm (8”) × H 200 mm (7 7/8”) × T 118 mm (4 5/8”) --2 row
   - Overall Size: W 210 mm (8 1/4") × H325 mm (12 3/4") × T 130 mm(5 1/8")
   - Inlet/Outlet: φ56 mm (2 1/4")
   - Material: 100%  Aluminum


While having the exchanger inside the heater chamber would be preferable, placing penetrations in the enclosure is not, especially during prototyping. The intercooler will set atop the enclosure, with an intake and exhause hose from each hose flange into the enclosure door.

There are no axial fans available off the shelf with service temperatures above 85 C. One exception was suggested by a user on Discord, which is only available to ship to the EU. Another helpful Discord user from the EU assisted with forwwarding a 150 C capable axial fan with the specifications:

|Type|Installation diameter|Productivity (air exchange), m³/h|Noise level, dB|Maximum operating temperature C °|Power max, W|Rotation frequency, rpm|Dimensions|Pressure, max, Pa|current, A.|Phase/voltage 50Hz|
|-------|-------|-------|-------|-------|-------|-------|-------|-------|-------|-------|
|60 m³/h|90|60|36|+150|16|2500|93x93x25|50|0.096|1f / 230V|

Supplier: K-Tech-Pro, Germany

A wire-lined silicone air hose duct in the 2.25" diameter will be used to transport the air from the chamber to the intercooler and back.


![image](https://github.com/levins-law/Spicy-CR-10/assets/74157293/b3ed046d-15b5-411e-85fb-8e165f75e4ec)
