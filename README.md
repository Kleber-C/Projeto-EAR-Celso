# e-AR (EAR) PROJECT - EMERGENCY VENTILATOR
This project was born because of CoVid19 pandemic.
The project Goal is to provide an emergency ventilator system to help CoVid19 serious cases using locally available resources. eAR was designed to meet specifications according to MHRA (UK) - Rapidly Manufactured Ventilator System and inspired by MIT E-Vent (USA) concepts and specs.

This is an OPEN HARDWARE - OPEN SOURCE PROJECT. 

DISCLAIMER: we will NOT take any responsability on devices built using partial or total information from this project. 
Any device used for life support and medical applications must meet all local requirements and they must be homologated by local regulatory agencies in ANY case.

The target is to run an entire ventilation system using an automotive car battery and an O2 can.
The initial project leader is Celso Ken Mori Monteiro, automotive designer with +30 yrs experience on automotive embedded systems
as OEM designer for customers as GM, Ford, VW, Fiat, Mercedes Benz, Scania, Navistar, Marcopolo, Agco...

The technology for first PCBs was downsized due to components availability in emerging countries so distributed production could be achieved even in small brazilian towns. The electronic parts are:
- PTH components
- Single-sided PCB, obtainable even by DIYs. 

Besides inclusive concept there is also a FR4 SMT version available for volume production.

Basic concepts:
- External FIO2 O2 + AIR mixer based on timed mechanical truck air valves and plastic bag container
- AMBU smasher based on car window motor due to availabilty and great mechanical characteristics. Motor reversion is necessary to allow dinamic changes of BPM, Tidal Volume, pressure ramping, I/E Ratio and Plateau Hold Time without ANY mechanical change.
- ECU based on Arduino Pro Mini (the most available in emerging countries) and SPI based IO expension
- 2 motor drive options: relay (need second adjustable supply or buck) and PWM driven mosfet driver

Project Evolution:
- full HW schematics and system component's description available on "EAR System Developer's HW Guide", portuguese only version
- PCB Gerbers available, Single Side PTH version, Motor driver on relay option only. Time and size were underestimated because we no longer use these old technologies. Released on March 30, 2020.
- Mech prototype phase 2 aproved, torque is OK and current is low.
- Gerbers of single sided boards on PTH components published on March 30, 2020. Time and size were underestimated because we no longer use these old technologies. 
- EAR System Developer's SW Guide released on March 30, 2020.
- Functional electronics prototype built and delivered on April 2, 2020. No changes in PCBs are necessary except hardware end-of-courses provided for EAR ECU Motor Driver Board. Test driven by firmware FW00 - focused on HW testing only. Reads input pots, control motor with reversal action, measures motor current and tests IO expansion board. All items are functional.
- FW00 published in April 3, 2020.
- Added Mosfet-based PWM Motor Driver and Absolute position sensor using a car fuel level sensor.
- First working mechanical+electrical prototype delivered in April 6, 2020.
- Added Pressure Sensor in April 7, 2020. First artificial lung is a balloon so first pressure profile was obtained. It Sounds promising.
- Firmware controls Tidal Volume and BPM according to Set Potentiometers. First functional firmware produce variable pressure ramps as needed, FW met 8-30 BPM dynamic range specification.
- Added motor cutoff in inspiratory phase according to pressure preset on pot Overpressure Threshold within 1cm H20 resolution.
- Added full mechanical design for functional AMBU compressing ARM in April 11, 2020
- Added in April 12, 2020: Motor Driver, mosfet NN version. Full Kicad design with schematics, PCB and Gerbers.
- Added in April 12,2020: eAR External watchdog Timer to increase eAR reliability. Full Eagle design with schematics, PCB and Gerbers.
- Added in April 13,2020: I/E selection (1:1, 1:2, 1:3 and 1:4) and Plateau Hold Time selection (150, 250, 500 and 1000ms hold on Plateau)
- Added in April 13,2020: Gol G3 tank level float sensor added as absolute position sensor. Increased linearity, resolution and availability
- Mech proto 3.2 added ball bearing in compression arm, currently performing cycling tests
- Added in April 15,2020; eAR Pressure sensor Board Design and PCB, MPX5010DP supported
- Added in April 21,2020: 10x10cm FR4 SMT single PCB design for volume production, verified design, send to production
- Added in April 21,2020: Mechanical proto 3.2 drawings delivered, functional design
- April 30, 2004: eAR FR4 Single-Board PCBs arrived, courtesy from Digicart/SC
- May 1st, 2020: eAR system reached 14 days of 24/7 operation, with 403,412 beathing cycles completed. eAR met minimum durability MHRA (UK) Spec with a prototype built on MDF, a window lift BDC motor and a 20-yrs-old chevy tank float sensor
- May 5, 2020: Multiple pressure sensor added, allowing almost any kind of linear pressure sensor to be connected to eAR system, including MPX5010, MPX10 almost all versions and packages including MPVZ and MP3V and experimental ultra-low-cost MPS20N0040D-S sensor
- May 12, 2020: Integrated EAR ECU tested, functional test OK. Some minor drilling errors corrected, some improvements done and new PCB generated. New mosfet driver option added in firmware as needed. Some components changed values due to standardization effort to ease production. eAR electronics is ready for mass production.
- May 23, 2020: Added first steel based eAR mechanical design, by Ricardo Suzuki. Arm sensor changed to DS 1901 non-contact TPS. 
- June 1st, 2020: Added R2 of mechanical design in two verions, geared arm and 4-linked-bars by Ricardo Suzuki

Pending:
- Software reliability improvements.
- Assisted Ventilation Firmware on hold. It can delay ANVISA aproval when requested.

Special thanks to all people that made this project real!
It's impossible to list all names involved, I apologize for forgetting someone.
The partial list follows:

Project Contributors, as they have joined this project
- Joannes Berque (FR): first design idea.
- Celso Monteiro: eletronics and firmware design, system conception and documentation.
- Diego Padilha and Lucas Pianizzer: electronics and mechanical design+prototyping. 
- Marcelo Pires: electronic CAD, schematics capture & PCB Design.
- Nicolai Rutkevich: mechanical concepts.
- Bruno Afogliatto: decontamination concepts.
- Gustavo Ortenzi: motor drive alteratives.
- Ricardo Suzuki: system concepts and mechanical design.
- Rodrigo Azevedo: organized Github Project.
- Douglas Esteves: interface with other projects.
- João Cardoso and Leonardo Afonso: Kicad Capture for Open Hardware.
- Andre Novelli e Victor Acioly: AMBU bags replacement.
- Flavio Alves: GUI design
- David Loos: electronics assembly

References:
- MIT E-Vent: human requirements and system conception ideas.
- MHRA (UK) Rapidly Manufactured Ventilator System

Healthcare professionals involved:
- Angelica Mammana M.D. helped stablishing specs and performed crytical analysis.
- Fernando Machado M.D. was the first contributing doctor.
- Lucio Flavio M.D.
- Ana Teresa Gama.

Project supporters:
- Fabio Knihs.
- Norberto Tomio.
- Gabriel Casagrande.
- Ivandro Ceccato.

Thanks to my family, special thanks to my dear wife Tissa and my children Joana, Gustavo and Leonardo, for their unlimited support and to all the people that prayed for this project, and God that inspired and guided me all the time.

