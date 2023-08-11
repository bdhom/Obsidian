## Description
The "TGL Service Base" library serves as the foundational framework for TGL C++ containers, offering essential services to support other TGL components. This library manages MQTT connections and provides general logging capabilities for TGL services. Moreover, it assumes responsibility for monitoring overall service health and heartbeat functionalities.

## Take-Aways
* Start Date: first commit - 2023-06-01
* End Date: last commit - 2023-08-03 (possible future work)
* Team Work Description: Mostly sole developer aside from CI/CD. Started from scratch
* Languages Used: C++, shell
* Tools/Frameworks Used: Docker, CMake, clang-format, git
* Platform: Embedded Linux

### Work Performed
* Developed "TGL Service Base" MQTT and logging functionalities for use in Docker containers running TGL C++ components
* Provided 3 ways to build a new service (inheriting service could modify):
	* Build from command line options
	* Build from a JSON config file
	* Build from environment variables
* Incorporated components for monitoring service health and sending heartbeats
* Created unit tests for end-to-end testing of MQTT pub/sub topics

### Accomplishments
* Learned about futures and detached processes in multi-threaded C++ applications

## Tasks

### Self-Created Tasks
- [ ] Update MQTT topics to fit confluence reference #TODO  ➕ 2023-07-28
- [ ] Remove the use of detached process and replace with futures/asyncs (std::launch::async??) #TODO  ➕ 2023-08-05
	- [ ] Have a proper clean-up for the futures (use wait_for(0)) ➕ 2023-08-05
	- https://putridparrot.com/blog/threads-promises-futures-async-c/
- [ ] Command handle to process individual commands from cmd line (baseservicebuilder) #BACKLOG  ➕ 2023-07-28
- [ ] Convert local time to GM/UTC time #TODO ➕ 2023-08-08
	https://en.cppreference.com/w/cpp/chrono/c/gmtime
- [x] Determine why CI/CD build is failing on the unit tests ➕ 2023-08-01 ✅ 2023-08-03
- [x] Handle messages that have no repsonse topic ➕ 2023-08-10 ✅ 2023-08-10
- [x] Implement send system event message method ➕ 2023-08-10 ✅ 2023-08-10

### Jira Tasks
