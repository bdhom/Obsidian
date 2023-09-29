## Description
Controls and GUI for a proofer and baker system utilized by fast-food chains such as Chic-Fil-A, Subway, etc.

## Take-Aways
### Work Performed
* Provided GUI support
* Incorporated a method for the user to calibrate the touchscreen
* Created unit tests for classes tied to the main functionalities of the PBC
	* Proofer
	* Oven
	* Trays
	* DB storing
* Implemented alarms that let the users know when the oven or proofer has completed a step in its process (and therefore may need interaction by the user, e.g. oven done, add seasoning, proofer done, etc.)
* Established database classes used to store recipe and global settings information that interfaced with on device sqlite databases (one for each language supported)
* Translation of strings from English to several languages
	* French
	* Spanish
	* Russian
	* Polish
	* German
	* Portuguese

### Acomplishments
- Learned how to interface C++ code w/ an sqlite database
- Learned the importance of using unit tests on critical classes/sections of code