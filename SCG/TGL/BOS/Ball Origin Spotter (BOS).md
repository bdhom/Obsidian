## Description
The "Ball Origin System" (BOS) is an application designed to precisely detect and locate a golf ball on its tee position and communicate this information seamlessly to MQTT consumers. The heart of this system lies in its machine learning (ML) models, trained to accurately identify both golf balls and clubs, and a ZED camera used for millimeter-accurate stereographic depth estimations. The ML models work in conjunction with TensorRT (models as TensorRT engine files), enabling real-time updates to consumers as soon as the designated ball, determined through a series of selected algorithms, is successfully located or in case it becomes lost. For the discovery phase, the following hardware was used:
* NVIDIA Jetson Xavier NX (J2021)
* ZED 2i Camera
Once the discovery phase ended, more sophisticated hardware was utilized for better performance:
* NVIDIA Jetson Orin NX (ZED Box)
* ZED X Camera

## Take-Aways
* Start Date: first commit - 2023-05-02
* End Date: last commit - 2023-07-07 (will have future work)
* Team Work Description: Sole developer. Started from scratch
* Languages Used: C++, python, shell
* Tools/Frameworks Used: ZED SDK, CUDA, TensorRT, YOLOv8, Docker, CMake, clang-format, git
* Platform: Embedded Linux

### Work Performed
* Conducted discovery for NVIDIA Jetson and ZED camera platforms running Docker containers with ML models for object detection and positioning/distance measurements
* Responsible for the entire application development process, integrating components for frame capture, inference, and MQTT communication
* Established tests for quality assurance of algorithms and trained models, ensuring the application's reliability and accuracy

### Accomplishments
* Learned about synchronization in multi-threaded C++ applications (knew some already for C and C#)
* Sped up image processing 25% on CPU side by parallelizing capture and inference functionalities (120 ms vs 160 ms) (on discovery hardware)
* FUTURE: Sped up % by parallelizing GPU side??
* FUTURE: Improved accuracy of measurements or object identification by finding an alternative algorithm??

## Tasks

### High Priority
- [ ] Setup the 8 new ZED Box's: #INPROG ➕ 2023-09-12 
	- [ ] Document/script the process for setting up a ZED Box
	- [x] Create shell script for starting docker container ✅ 2023-09-14
	- [x] Create service for running docker script and doing a docker pull if applicable ✅ 2023-09-14
	- [x] Create mounting points for config.json?? ✅ 2023-09-14
	- [x] Create service names in config.json based on: https://fullswing.atlassian.net/wiki/spaces/TGL/pages/3367567361/5.6+Pub+Sub+Message+Protocol#Application-Level-Message-Listing 📅 2023-09-19 ✅ 2023-09-16
- [ ] Create specialized worker threads dedicated for the purposes of speeding up the inference bottle-neck  #INPROG  ➕ 2023-09-14 📅 2023-09-18 
	- [ ] Post-inference worker
	- [ ] Pre-inference worker?
- [ ] Fix neural depth model not downloading entirely on container image #TODO ➕ 2023-09-18
- Below - Items discussed w/ Jon
- [ ] Clean up stop record after X frames #TODO ➕ 2023-09-21
	- Jon may be handling this
- [ ] Use service health for camera state (poor if error else good) #TODO ➕ 2023-09-19
- [ ] Create stability in gaining access to the camera #TODO ➕ 2023-09-18 
	- [ ] May need to reset/restart the camera if unable to open
	- [ ] Ensure works on Windows
	- [ ] Ensure works on ZED Box
	- Keep in mind that ZED Box container is currently unable to obtain access to the "zed_x_daemon" service
- [x] Add entry point to dev container image #TODO ➕ 2023-09-19 ✅ 2023-09-19
- [x] Pass command line arguments from "docker run ..." to start.sh #TODO ➕ 2023-09-19 ✅ 2023-09-19
- [x] Create a dev docker container that holds the app binary and supporting items #TODO ➕ 2023-09-14 📅 2023-09-15 ✅ 2023-09-16
- [x] Fix testing functionality #TODO ➕ 2023-09-16 ✅ 2023-09-17
- [x] Configurable record path #TODO ➕ 2023-09-16 ✅ 2023-09-17

### Self Created Tasks
- [ ] Object memory #TODO ➕ 2023-07-28 
	* Objects should be remembered if it is not too far from last position over a specified amount of frames
		* Exception to this would be [[Ball Origin Spotter (BOS)#^f068e4|Club Obstruction Filter]]
- [ ] Club obstruction filter #TODO ➕ 2023-07-28  ^f068e4
	* Ball should not be removed from memory if obstructed by club.
	* If club obstruction algorithm selected, ball shall be selected as "the ball" that program cares about.
- [ ] Add weighted positioning calculation?? #BACKLOG  ➕ 2023-07-28 @completed(2023-08-07T14:29:44)
- [ ] Implement dynamic ROI #TODO ➕ 2023-07-28 
- [ ] Remove position filter #BACKLOG ➕ 2023-07-28 
- [ ] Look into providing parallelized GPU support #TODO ➕ 2023-07-28
- [ ] Look into getting an SDK running on windows (WSL) #BACKLOG  ➕ 2023-08-04
- [ ] Look into providing depth information from the 3D point cloud rather than the depth mappings #TODO ➕ 2023-08-05 
	* Reason for research: https://www.stereolabs.com/docs/depth-sensing/using-depth/#measuring-distance-in-point-cloud
- [ ] Determine why ZED X daemon is not able to be reached by Docker container and if needed #TODO ➕ 2023-08-05 
	- [ ] See if this will allow us to restart the camera if it is not responding ➕ 2023-08-05
- [ ] Rename variables to fit standard (yolov8) #BACKLOG ➕ 2023-08-04
- [ ] Ensure that object positioning coordinate system are same as documentation #TODO ➕ 2023-08-06 
- [ ] Provide VSCode settings file if useful for building alone (w/o Visual Studio) #TODO ➕ 2023-08-28
- [ ] Look into providing .yml files for zed initialization #TODO ➕ 2023-09-07
- [ ] Adjust resolution to be highest for each camera supported?? #TODO ➕ 2023-09-07
- [ ] Cleanup #TODO ➕ 2023-09-16 
	- [ ] Condense converter and helper functions
	- [ ] 
- [x] Return old ZED Box #BACKLOG ➕ 2023-08-28 ✅ 2023-09-12
- [x] Remove relative offset for radar #TODO ➕ 2023-08-28 ✅ 2023-09-07
- [x] Setup new ZED Box #INPROG ➕ 2023-08-28 ✅ 2023-09-01
	- [x] Ensure that new ZED Box is capable of working as quickly as previous ZED Box with latest conversion method ➕ 2023-08-31 ✅ 2023-09-01
- [x] Transition program to remove use of third-party repo to convert models #INPROG ➕ 2023-08-23 ✅ 2023-08-28
- [x] Test new ZED X Camera w/ 2 cameras going - report back the fps #TODO ➕ 2023-08-14 ✅ 2023-08-23
- [x] Ensure that above description is correct/fact-checked ➕ 2023-07-29 ✅ 2023-07-30
- [x] Update submodule once TGL Service Base updated?? ➕ 2023-07-28 ✅ 2023-08-04
- [x] Get rid of deprecated warnings ➕ 2023-07-28 ✅ 2023-08-04
- [x] Rename from "detection"/"zed-detection" to "Ball Origin Spotter"/"BOS" #INPROG ➕ 2023-08-04 @completed(2023-08-07T15:10:41)

### Jira Tasks
- [ ] TGLBOS-76: Implement video recording and synchronization to S3 #INPROG ➕ 2023-09-07
	- [ ] TGLBOS-84: Implement video recording
		- Start record on tracking arm
		- End record after hit
		- ~~Configurable seconds after hit remain recording~~
	- [ ] TGLBOS-85: Implement synchronization to S3
- [ ] TGLBOS-82: Start inference on tracking arm and end inference on hit #INPROG ➕ 2023-09-07 
	- Inference will stay the same
	- Start recording on arm and end X configurable seconds after hit
- [x] TGLBOS-28: Set up object classification in ROI #INPROG ➕ 2023-08-08 ✅ 2023-08-29
- [x] TGLBOS-72: Create an SDK/CMake or image based solution for working on ZED Box in parallel with other developers #TODO ➕ 2023-08-10 ✅ 2023-08-18
- [x] TGLBOS-27: Set up object detection in ROI #INPROG ➕ 2023-08-08 @completed(2023-08-08T15:00:26)
	- Set up scanning area to cover the ROI defined in the requirements. The device should scan as many slices as needed to scan at full resolution without downsizing the image. [https://fullswing.atlassian.net/wiki/spaces/TGL/pages/3373269154/2.4.1+Ball+Origin+Spotter](https://fullswing.atlassian.net/wiki/spaces/TGL/pages/3373269154/2.4.1+Ball+Origin+Spotter)

## Notes
### Setup on Windows
Build BOS for windows:
``` shell
cmake -B build -S . -DCMAKE_TOOLCHAIN_FILE="C:\dev\vcpkg\scripts\buildsystems\vcpkg.cmake" -DTENSORRT_PATH="C:\Users\BrycenDhom\Installers\TensorRT-8.6.1.6.Windows10.x86_64.cuda-11.8\TensorRT-8.6.1.6"
cmake --build build
```
