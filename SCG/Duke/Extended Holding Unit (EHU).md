
## Description
The "Extended Holding Unit" (EHU) is a partial porting of a previous project, the [[Proofer Baker Center (PBC)]], to fit new hardware that fast-food restaurants (Popeye's mainly) will use to hold food (chicken) for extended periods of time while keeping the holding container within the recommended humidity and temperature ranges.

## Take-Aways
* Start Date: first commit - 2023/07/13
* End Date: last commit - 2023/09/29
* Team Work Description: Team of 2 w/ 1 senior dev as a reviewer
* Languages Used: C++
* Tools/Frameworks Used: Qt (GUI)
* Platform: Embedded Linux

### Work Performed
* Implemented methods to digest calibration values over CAN bus and relay these values up to the database to be stored and used after EOL (i.e. to be used in the field)
* Restructured fault system to support finite state machines for each type of fault. Faults have several different severity levels which describe different states and behaviors for other code that needs to observer the faults

### Accomplishments
* Learned how to use a CAN bus analyzer
* Learned the basic format of a CAN message frame

## Tasks

### High Priority
### Backlog
- [ ] EHU-214: Calibration values not showing correctly #BACKLOG ➕ 2023-08-04
- [ ] EHU-217: As a EHU user I would like to implement the High Humidity faults on UI the Flextech #BACKLOG  ➕ 2023-08-08
- [ ] EHU-227: Humidity representation - 1% difference #BACKLOG ➕ 2023-08-18
	- iomodule.cpp:429 - "//Temperature compensation from HTU3500 data sheet (based on oven rtd...)"
	- iomodule.cpp - differences in # define's prefixed w/ "HUMIREL3500" vs flextech code
- [ ] EHU-196: Engineering testing validation #BACKLOG ➕ 2023-07-31
### TODO
- [ ] EHU-265: exploratory testing on EHU #TODO  ➕ 2023-09-19 
### In Progress
- [ ] EHU-267: As a EHU user I would like to hear an alarm when a fault is encountered. #INPROG ➕ 2023-09-19 
### Completed
- [x] EHU-267: Fix System Status Page Crash  #TODO ➕ 2023-09-14 ✅ 2023-09-19
- [x] EHU-176: As an EHU user I would like to validate that the EHU is able to proceed through the EOL process #TODO ➕ 2023-07-31 ✅ 2023-09-19
- [x] Fix for JSON mess up #INPROG ➕ 2023-09-11 ✅ 2023-09-11
	- Need to allow database implementation to grab correct members from JSON in library. This can be achieved by 2 methods
		- Allow a special function to convert from db json to class type
		- Or update db to hold specified types
- [x] EHU-243: GUI STAT1 CAN message sending #INPROG ➕ 2023-08-24 ✅ 2023-09-01
- [x] EHU-38: As a EHU user I would like to implement high humidity faults #TODO ➕ 2023-08-04 ✅ 2023-08-07
- [x] EHU-197: Yocto Learning ➕ 2023-07-31 ✅ 2023-08-04
- [x] EHU-180: Create a firmware version at end of sprint and have it deployable on an actual unit for control comparison testing and qmetry testing ➕ 2023-07-31 ✅ 2023-08-04
- [x] EHU-184: Setup testing and developer environment for EHU ➕ 2023-07-11 ✅ 2023-07-14
- [x] EHU-174 & EHU-194: Create CANbus handler to store calibration value on the new controller (phase 2) ➕ 2023-07-21 ✅ 2023-07-24
- [x] EHU-195: Validation testing of EOL line of PEHU firmware with CANbus analyzer ➕ 2023-07-28 ✅ 2023-07-29
- [x] Create a task for fault manager rework #TODO ➕ 2023-08-08 @completed(2023-08-08T18:02:00)
- [x] Create a task for UI fault flow rework #TODO ➕ 2023-08-08 @completed(2023-08-08T18:02:03)
- [x] QML FaultType conversions (EHU-225) #INPROG ➕ 2023-08-10  @completed(2023-08-14T12:27:00)
- [x] EHU-224: As a developer I would like to convert from PBC fault flow to EHU fault flow #INPROG ➕ 2023-08-10 ✅ 2023-08-17
	- [x] EHU-225: Convert PBC fault types to EHU fault types ➕ 2023-08-10 ✅ 2023-08-14
	- [x] EHU-226: Convert active/inactive states to active/inactive states with severity levels ➕ 2023-08-10 ✅ 2023-08-14
	- [x] Convert proofer references in faults and iomodule. Move to oven if possible ➕ 2023-08-14 ✅ 2023-08-14
- [x] EHU-219: As a developer I would like to implement a fault aggregate/model class #INPROG ➕ 2023-08-10 ✅ 2023-08-18
- [x] EHU-220: As a developer I would like to implement a fault page stack #INPROG ➕ 2023-08-18 ✅ 2023-08-22
- [x] EHU-199: As a EHU user I would like to store and to be able set a default of the popeyes color mode at manufacturing time #INPROG ➕ 2023-09-01 ✅ 2023-09-05
- [x] EHU-145: As a EHU user I would like to load a preset list of Popeyes recipe at manufacturing time via JSON file  into the database #INPROG ➕ 2023-09-01 ✅ 2023-09-05

## Notes
- EHU-265: Exploratory Testing Notes
	- Findings:
		- Fault page resources need translations
		- Oven RTD fault not showing fault page stack immediately when high temp?
		- Missing or incomplete translations
			- Boot screen
			- Contact Us page
			- System Status page
			- Diagnostics page
			- Config Settings page
			- Color Mode page
			- 4 Tray Mode page
			- Tools Settings page
			- RH Probe Offset page
			- Recipe Settings page
			- Cavity Settings page
			- Recipe Selection page
			- Recipe Edit page
			- Tray Config page
			- Sensor Cal page
		- Cavity setpoint on centigrade mode
		- 
	- Items to explore:
		- ~~Translations of back menus and text~~
		- Marketing Requirements:
			- Runtime Screen:
				- ~~Boot Screen~~
				- Settings Selection
				- ~~Audible Alarms~~
				-  ~~Start Tray~~ 
				- ~~Stop Tray~~
				- Expire Tray
				- ~~Transfer Product Messaging~~
			- States:
				- Idle
				- Preheating Indicator
				- Soak
				- Ready
				- Faulted State
			- Beeper:
				- Timer Expiration
				- Beeper On/Off in config
			- Recipe Manager:
				- Cavity Control:
					- Water Gain
					- Humidity
					- RH% Setpoint
					- Vent Fan On/Off RH%
				- Recipe Edit:
					- Name
					- Hold Time
				- Tray Selector
			- Fault Messaging:
				- ~~Low Temperature Fault~~
				- ~~High Temperature Fault~~
				- Critical Sensor Faults:
					- CAN Loss
					- Oven RTD
					- Ring RTD
					- RH Probe
				- High Humidity
			- Firmware Updates:
				- From USB
			- EOL:
				- Recipe Load
				- AutoCal
				- EOL