## Description
The "Full Swing KIT Launch Monitor" (LM) is a device used to track a golf ball while being driven. It measures various data points throughout a golf balls trajectory using its 4k camera and radar system to calculate items such as carry distance and total, ball speed, ball spin, pitch, etc. The firmware created on the digital board was used to process data from the radar board and camera and communicate results to a connected app and to AWS for historical recall purposes. Firmware also handled several other responsibilities such as:
* Managing updates when an OTA was pushed from AWS
* Providing a GUI for the user to update device settings/modes and read shot data (rather than only being able to interact w/ on phone)

## Take-Aways
* Start Date: 2021-02-15
* End Date: last commit - 2023-07-13
* Team Work Description: Large team (8). Existing code base
* Languages Used: C++, shell
* Tools/Frameworks Used: Qt (GUI)
* Platform: Embedded Linux
### Work Performed
- Performed regression tests to find bugs before release and ensure features work as intended
- Maintenance work:
	- Troubleshooting and various bug fixes
	- Update manager fixes
	- [[LM EMMC Wear Testing]]
- Integrated functionality for network manager to connect with unsecured networks. Previously firmware only supported connecting to secure Wi-Fi access points
- Implemented network lists in order for network manager to connect to previously connected Wi-Fi access points. Previously firmware only "remembered" one network (i.e. when user wanted to connect to a different network, it would erase the previous one)

### Accomplishments
- Learned how SWUpdate and AWS OTA updates work
- Learned how Linux networking works with WPA supplicant, DHCP client, and Network Manager

## Tasks

## Notes
