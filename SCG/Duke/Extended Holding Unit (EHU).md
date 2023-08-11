
## Description
The "Extended Holding Unit" (EHU) is a partial porting of a previous project, the [[Proofer Baker Center (PBC)]], to fit new hardware that fast-food restaurants (Popeye's mainly) will use to hold food (chicken) for extended periods of time while keeping the holding container within the recommended humidity and temperature ranges.

## Take-Aways
* Start Date: first commit - 2023/07/13
* End Date: last commit - 2023/08/04
* Team Work Description: Team of 2
* Languages Used: C++
* Tools/Frameworks Used: Qt (GUI)
* Platform: Embedded Linux

### Work Performed
* Implemented methods to digest calibration values over CAN bus and relay these values up to the database to be stored and used after EOL (i.e. to be used in the field)

### Accomplishments
* Learned how to use a CAN bus analyzer
* Learned the basic format of a CAN message frame

## Tasks

### Self-Created Tasks
- [x] Create a task for fault manager rework #TODO ➕ 2023-08-08 @completed(2023-08-08T18:02:00)
- [x] Create a task for UI fault flow rework #TODO ➕ 2023-08-08 @completed(2023-08-08T18:02:03)
- [ ] QML FaultType conversions (EHU-225) #INPROG ➕ 2023-08-10 

### Jira Tasks
- [ ] EHU-176: As an EHU user I would like to validate that the EHU is able to proceed through the EOL process #TODO ➕ 2023-07-31
- [ ] EHU-196: Engineering testing validation #TODO ➕ 2023-07-31
- [ ] EHU-214: Calibration values not showing correctly #BACKLOG ➕ 2023-08-04
- [ ] EHU-217: As a EHU user I would like to implement the High Humidity faults on UI the Flextech #TODO ➕ 2023-08-08
- [ ] EHU-219: As a developer I would like to implement a fault aggregate/model class #INPROG  ➕ 2023-08-10
- [ ] EHU-224: As a developer I would like to convert from PBC fault flow to EHU fault flow #INPROG ➕ 2023-08-10
	- [ ] EHU-225: Convert PBC fault types to EHU fault types ➕ 2023-08-10
	- [ ] EHU-226: Convert active/inactive states to active/inactive states with severity levels ➕ 2023-08-10
- [x] EHU-38: As a EHU user I would like to implement high humidity faults #TODO ➕ 2023-08-04 ✅ 2023-08-07
- [x] EHU-197: Yocto Learning ➕ 2023-07-31 ✅ 2023-08-04
- [x] EHU-180: Create a firmware version at end of sprint and have it deployable on an actual unit for control comparison testing and qmetry testing ➕ 2023-07-31 ✅ 2023-08-04
- [x] EHU-184: Setup testing and developer environment for EHU ➕ 2023-07-11 ✅ 2023-07-14
- [x] EHU-174 & EHU-194: Create CANbus handler to store calibration value on the new controller (phase 2) ➕ 2023-07-21 ✅ 2023-07-24
- [x] EHU-195: Validation testing of EOL line of PEHU firmware with CANbus analyzer ➕ 2023-07-28 ✅ 2023-07-29

## Notes