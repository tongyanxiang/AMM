# Body Sensor Network (BSN)
BSN is a real-time health monitoring system based on a wireless sensor network. It consists of six sensors that collect different types of vital signs (e.g., blood oxygen, heart rate, body temperature, etc.) and a data processing hub that provides an overall health assessment. The power consumption of each sensor is determined by its sampling rate (which can be adjusted remotely), and its sensing
noise (which is determined by the environmental uncertainty). In a self-adaptive BSN, each of the sensors is controlled by a PI-based managing system that adjusts the sensor’s power consumption to a setpoint by changing the sampling rate with a control signal.

We extend the BSN (https://github.com/lesunb/bsn) and implement our AMM mechanism (i.e., activebsn.zip).


## Implementation
* AMM implementation of BSN is as follows:
	* The activebsn/controlbsn directory implements control-based self-adaptive BSN.
	* The activebsn/controlbsn/src/sa-bsn/simulation directory contains sensor **environmental input** file.
	* The activebsn/controlbsn/src/sa-bsn/configurations/system_manager/**strategy_enactor.launch** provides different **AMM’s alternatives** of BSN runs.
	* The activebsn/supervision directory contains **AMM** (in subfolder *detectors*).
	* The activebsn/main.sh is the script of running BSN.


## Installation
* Requirements
	* Ubuntu 20.04 LTS
	* [ROS Noetic](http://wiki.ros.org/noetic/Installation/Ubuntu)
	* Python 3.8.10 (with numpy, scikit-learn, scipy, and cvxopt)
	
* Unzip *activebsn.zip*

* Go to subfolder *activebsn/controlbsn*:
	* Compile AMM implementation of BSN:
		```
		cd activebsn/controlbsn && 
		rosdep install --from-paths src --ignore-src -r -y && 
		catkin_make
		```
	
	* Source the setup.bash inside the catkin workspace:
		```
		echo "source ~/activebsn/controlbsn/devel/setup.bash" >> ~/.bashrc
		source ~/.bashrc
		```


## Execution
* Run the simulation
    ```
    cd activebsn
    ./main.sh
    ```
	* The trace files are in subfolder **activebsn/controlbsn/src/sa-bsn/system_manager/enactor/traces*.
	* You can choose different **AMM’s alternatives** of BSN runs by configuring **strategy_enactor.launch** in subfolder *activebsn/controlbsn/src/sa-bsn/configurations/system_manager*
    ```
	...
	<param name="supervision_type" type="str" value="AMM" />
	<param name="AS_trigger_mode" type="str" value="combine_trigger" /> 
	<param name="AS_design_mode" type="str" value="optimal_design" />     
	...
    ```
	
* Conduct experiments
	* The running traces of BSN experimental configurations are collected in folder *BSNExperimentalConfigurations*. Please download all traces from the [Dataset](https://drive.google.com/file/d/1P_gp78KR33lDNtl0nnGSOyPA59on3kYK/view?usp=drive_link).
	* Based the collected traces, you can calculate the effectiveness (RQ1) and usefulness (RQ2) of BSN'S AMM implementation.
    * Also, you can get resource consumption (RQ3) by monitoring BSN simulation runs	