## Description
The "Full Swing KIT Launch Monitor" (LM) is a device used to track a golf ball while being driven. It calculates various data points using its camera and radar systems.

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

### Self-Created Tasks
- [ ] Expand on description of the LM as it is currently lackluster ➕ 2023-08-06

### JIRA Tasks

## Notes
