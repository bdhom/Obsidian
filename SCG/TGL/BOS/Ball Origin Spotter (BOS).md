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
- [x] Rename from "detection"/"zed-detection" to "Ball Origin Spotter"/"BOS" #INPROG ➕ 2023-08-04 @completed(2023-08-07T15:10:41)
- [ ] Rename variables to fit standard (yolov8) #BACKLOG ➕ 2023-08-04
- [ ] Ensure that object positioning coordinate system are same as documentation #TODO ➕ 2023-08-06 
- [x] Ensure that above description is correct/fact-checked ➕ 2023-07-29 ✅ 2023-07-30
- [x] Update submodule once TGL Service Base updated?? ➕ 2023-07-28 ✅ 2023-08-04
- [x] Get rid of deprecated warnings ➕ 2023-07-28 ✅ 2023-08-04

### Jira Tasks

