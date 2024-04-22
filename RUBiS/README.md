# Rice University Bidding System (RUBiS)
RUBiS is a web auction system that can adapt to workload/network changes by adjusting the number of servers to satisfy quality-of-service levels. 

We extend a [RUBiS simulator](https://github.com/cps-sei/swim) and implement our AMM mechanism (i.e., activeRUBiS.zip).


## Implementation
* AMM implementation of RUBiS is as follows:
	* The activeRUBiS/simulations/rubisPIC directory contains system configuration (e.g., rubisPIC.ini) and system architecture (e.g., rubisPIC.ned) files.
	* The activeRUBiS/simulations/workload directory contains user workloads (i.e., **environmental input**).
	* The activeRUBiS/simulation/**rubisConfig.xml** provides different **AMM’s alternatives** of RUBiS runs.
	* The activeRUBiS/src/controlRUBiS directory implements control-based self-adaptive RUBiS.
	* The activeRUBiS/src/supervision directory contains **AMM** (in subfolder *detectors*).
	* The activeRUBiS/main.sh is the script of running RUBiS.


## Installation
* Requirements
	* Ubuntu 20.04 LTS
	* OMNeT++ 6.0
	* Boost 1.65.1
	* Python 3.8.10 (with numpy, scikit-learn, scipy, and cvxopt)
	* jdk11
	* Pydev10.0.0 

* Download OMNeT++ 6.0 and install it following the installation guide.

* Make sure that OMNeT++ bin directory is in the PATH, otherwise add it:
	```
	export PATH=$PATH:/home/your path/omnetpp-6.0/bin
	```
   
* Install boost
   ```
   sudo apt-get install libboost-all-dev
   ```
   
* Install required packages of Python3: numpy, scikit-learn, scipy and cvxopt
	```
	sudo apt install python3-pip
	pip3 install numpy
	pip3 install scikit-learn (scipy)
	pip3 install cvxopt
	```

* Unzip the files **queueinglib.zip** and **activeRUBiS.zip** in *RUBiS* directory

* Go to *RUBiS* and compile queueinglib
	```
	cd queueinglib
	make
	```
   
* Go to *RUBiS* and compile activeRUBiS
	```
	cd activeRUBiS
	make  
	```
   
* Configure Python interpreter to enable the calling of python script from C++
	* Install jdk11
	```
	sudo apt install default-jre
	sudo apt install default-jdk
	```
   
   	* Install and configure Pydev10.0.0 in OMNeT++ 6.0

   
## Execution
* Run the simulation
    ```
    cd RUBiS/activeRUBiS
    ./main.sh
    ```
	* The trace files are in subfolder *activeRUBiS/simulations/traces*.
	* You can choose different **AMM’s alternatives** of RUBiS runs by configuring **rubisConfig.xml** in subfolder *activeRUBiS/simulation*
	```
	...
	<serviceASupervisionTrigger>true</serviceASupervisionTrigger>
	<serviceAAuxiliarySignalTriggerMode>combine_trigger</serviceAAuxiliarySignalTriggerMode>
	<serviceAAuxiliarySignalDesignMode>optimal_design</serviceAAuxiliarySignalDesignMode>
	...
	```
		
* Conduct experiments
	* The running traces of RUBiS experimental configurations are collected in folder *RUBiSExperimentalConfigurations*. Please download all traces from the [Dataset](https://drive.google.com/file/d/1RbtlHdVRGXy9bc2AyQ0hFcu3cE9LMXCy/view?usp=drive_link).
	* Based the collected traces, you can calculate the effectiveness (RQ1) and usefulness (RQ2) of RUBiS'S AMM implementation.
    * Also, you can get resource consumption (RQ3) by monitoring RUBiS simulation runs	