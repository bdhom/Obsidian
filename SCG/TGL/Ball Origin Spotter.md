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

### Work Performed
* Conducted discovery for NVIDIA Jetson and ZED camera platforms running Docker containers with ML models for object detection and positioning/distance measurements
* Responsible for the entire application development process, integrating components for frame capture, inference, and MQTT communication
* Established tests for quality assurance of algorithms and trained models, ensuring the application's reliability and accuracy

### Acomplishments
* Learned about synchronization in multi-threaded C++ applications (knew some already for C and C#)
* Sped up image processing 25% on CPU side by parallelizing capture and inference functionalities (120 ms vs 160 ms) (on discovery hardware)
* FUTURE: Sped up % by parallelizing GPU side??
* FUTURE: Improved accuracy of measurements or object identification??

## Tasks

### Self Created Tasks
- [ ] Object memory ➕ 2023-07-28
	* Objects should be remembered if it is not too far from last position over a specified amount of frames
		* Exception to this would be [[Ball Origin Spotter#^f068e4|Club Obstruction Filter]]
- [ ] Club obstruction filter ➕ 2023-07-28  ^f068e4
	* Ball should not be removed from memory if obstructed by club.
	* If club obstruction algorithm selected, ball shall be selected as "the ball" that program cares about.
- [ ] Add weighted positioning calculation ➕ 2023-07-28
- [ ] Implement dynamic ROI ➕ 2023-07-28 
- [ ] Remove position filter ➕ 2023-07-28 
- [ ] Get rid of deprecated warnings ➕ 2023-07-28 
- [ ] Update submodule once TGL Service Base updated?? ➕ 2023-07-28 
- [ ] Look into providing parallelized GPU support ➕ 2023-07-28 
- [x] Ensure that above description is correct/fact-checked ➕ 2023-07-29 ✅ 2023-07-30

### Jira Tasks

