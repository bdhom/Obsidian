## Description
"ZED Test Metrics" is a C#/.NET based application that consumes post-execution data, in the form of JSON files, from the "Ball Origin Spotter" (BOS) and the "ZED Capture" applications. It provides analytics on how accurate and precise any given set of models and algorithms were for the BOS for each test run based on truth data gathered pre-execution by the "ZED Capture" application.

## Take-Aways
* Start Date: first commit - 2023/05/11
* End Date: last commit - 2023/06/02
* Team Work Description: Sole developer. Started form scratch
* Languages Used: C#
* Tools/Frameworks Used: .NET, git
* Platform: Windows
### Work Performed
* Support JSON deserialization to extract truth and test data for analysis
* Created analytics that gave data points and graphs based on:
	* accuracy and precision at a depth of X
	* accuracy and precision at an offset of X
	* average processing time
	* missed test points

### Accomplishments


## Tasks

### Self-Created Tasks
- [ ] Ensure that all data to be gathered from BOS test is correct ➕ 2023-07-29
- [ ] Create statistical data points for min, max, and average for certain items ➕ 2023-07-28