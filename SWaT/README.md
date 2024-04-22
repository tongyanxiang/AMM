# Secure Water Treatment testbed (SWaT)
SWaT is a fully operational scaled-down water treatment plant that produces doubly-filtered drinking water. SWaT consists of five water-processing tanks, as well as the pipes that connect those tanks. The in-coming valve and out-going valve of each tank can be controlled remotely via network. The objective of a self-adaptive SWaT system is to enable safe (e.g., no overflow or underflow in any of the tanks) and efficient (e.g., maximum clean water production) water filtering under different environmental situations (e.g., the
initial water level of the five tanks, and the in-coming water flow of the first tank). 

We extend a [SWaT simulator](https://sav.sutd.edu.sg/research/physical-attestation/sp-2018-paper-supplementary-material/) and implement our AMM mechanism (i.e., activeSWaT.zip).


## Implementation
* AMM implementation of SWaT is as follows:
	* The activeSWaT/controlSWaT directory implements control-based self-adaptive SWaT.
	* The activeSWaT/supervision directory contains **AMM** (in subfolder detectors).
	* The activeSWaT/main.py implements SWaT's main funtion, it sets initial water tank levels (i.e., **environmental input**) and implements water treatment processes with different **AMM’s alternatives**.


## Installation
* Requirements
	* Ubuntu 20.04 LTS
	* Python 3.8.10 (with numpy, scikit-learn, scipy, and cvxopt)


## Execution
* Run the simulation
    ```
	python3 main.py
    ```
	* The trace files are in subfolder *activeSWaT/controlSWaT/trace*.
	* You can choose different **AMM’s alternatives** of SWaT runs by initialize supervision modules in *main.py*
	```
	...
	detector = AMM(False, 'combine_trigger', 'optimal_design')
	switcher = Switcher()
	...
	```

* Conduct experiments
	* The running traces of SWaT experimental configurations are collected in folder *SWaTExperimentalConfigurations*. Please download all traces from the [Dataset](https://drive.google.com/file/d/1Qfm2e2jApgXcjIQI3-ks4Cn-DPss9l5D/view?usp=drive_link).
	* Based the collected traces, you can calculate the effectiveness (RQ1) and usefulness (RQ2) of SWaT'S AMM implementation.
    * Also, you can get resource consumption (RQ3) by monitoring SWaT simulation runs	