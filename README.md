# AMM (Active Monitoring Mechanism）

**AMM** is a solution for detecting model deviation in control-based self-adaptive systems with vague observation. Given runtime measurements of a control-based self-adaptive system, AMM generates an active control signal if needed and gives an alarm when model deviation is detected.

* **Research paper**: “Active Monitoring Mechanism for Control-based Self-Adaptive Systems” (FSE'24)
    * [Paper preprint (PDF)](https://github.com/tongyanxiang/AMM/tree/main/AMM-fse2024.pdf)
	
* **Research artifact**
	* [BSN](https://github.com/tongyanxiang/AMM/tree/main/BSN) contains AMM implementation with a control-based self-adaptive health monitoring system and presents tracing files of five experimental configurations.
    * [RUBiS](https://github.com/tongyanxiang/AMM/tree/main/RUBiS) contains AMM implementation with a control-based self-adaptive web auction system and presents tracing files of five experimental configurations.
	* [SWaT](https://github.com/tongyanxiang/AMM/tree/main/SWaT) contains AMM implementation with a control-based self-adaptive water treatment system and presents tracing file of three experimental configurations.
    * [Dataset](https://drive.google.com/drive/folders/1NwNFJ8foMmrPa-Q07GTOMBx7YDD221v1?usp=drive_link) presents tracing files of all experimental configurations.

* **Installation and execution**
	* Clone the AMM artifact.
		```
		git clone https://github.com/tongyanxiang/AMM.git
		```
	  
	* Go to the subfloder to install and execute AMM implementation, the instructions of each implementation are shown in subfloder's README file. The **AMM artifact** is organized as follows:
		```
		.
		├── BSN
			├── BSNExperimentalConfigurations
			└──...
			├── activebsn.zip
			└── README.md: Installation and execution instructions of AMM implementation
		├── RUBiS
			├── RUBiSExperimentalConfigurations
				└──...
			├── activeRUBiS.zip	
			├── queueinglib.zip	
			└── README.md: Installation and execution instructions of AMM implementation 
		├── SWaT
			├── SWaTExperimentalConfigurations
				└──...
			├── activeSWaT.zip
			└── README.md: Installation and execution instructions of AMM implementation
		├── AMM-fse2024.pdf: preprint paper
		├── Licence.md
		├── README.md: overall instructions of the artifact
		```