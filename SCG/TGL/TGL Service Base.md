## Description
The "TGL Service Base" library serves as the foundational framework for TGL C++ containers, offering essential services to support other TGL components. This library manages MQTT connections and provides general logging capabilities for TGL services. Moreover, it assumes responsibility for monitoring overall service health and heartbeat functionalities.

## Take-Aways
* Start Date: first commit - 2023-06-01
* End Date: last commit - 2023-07-17 (possible future work)
* Team Work Description: Sole developer. Started from scratch

### Work Performed
* Developed "TGL Service Base" MQTT and logging functionalities for use in Docker containers running TGL C++ components
* Provided 3 ways to build a new service (inheriting service could modify):
	* Build from command line options
	* Build from a JSON config file
	* Build from environment variables
* Incorporated components for monitoring service health and sending heartbeats
* Created unit tests for end-to-end testing of MQTT pub/sub topics

### Acomplishments
* Learned about detached processes in multi-threaded C++ applications (fire and forget)

## Tasks

### Self-Created Tasks
- [ ] Update MQTT topics to fit confluence reference ➕ 2023-07-28
- [ ] Command handle to process individual commands from cmd line (baseservicebuilder) ➕ 2023-07-28

### Jira Tasks
