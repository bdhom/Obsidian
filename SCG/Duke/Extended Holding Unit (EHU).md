
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

### Jira Tasks
- [x] EHU-184: Setup testing and developer environment for EHU ➕ 2023-07-11 ✅ 2023-07-14
- [ ] EOL Validation and Testing ➕ 2023-07-21
    - [x] EHU-174 & EHU-194: Create CANbus handler to store calibration value on the new controller (phase 2) ➕ 2023-07-21 ✅ 2023-07-24
    - [x] EHU-195: Validation testing of EOL line of PEHU firmware with CANbus analyzer ➕ 2023-07-28 ✅ 2023-07-29
    - [ ] EHU-176: As an EHU user I would like to validate that the EHU is able to proceed through the EOL process ➕ 2023-07-31 
- [x] EHU-197: Yocto Learning ➕ 2023-07-31 ✅ 2023-08-04
- [x] EHU-180: Create a firmware version at end of sprint and have it deployable on an actual unit for control comparison testing and qmetry testing ➕ 2023-07-31 ✅ 2023-08-04
- [ ] EHU-196: Engineering testing validation ➕ 2023-07-31
- [ ] EHU-38: As a EHU user I would like to implement high humidity faults ➕ 2023-08-04
- [ ] EHU-214: Calibration values not showing correctly ➕ 2023-08-04

## Notes
{{notes}}