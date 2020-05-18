Reinforcement Learning (Q-Learning) Master Files

This contains the base files for the RL/Q-Learning Framework developed by Cameron Maras and Gregory Delipei.

This code works in conjuction with the Studsvik SIMULATE-3 nodal code using pre-defined fuel inventories.


The file user_input.py contains the user defined input for the SIMULATE portion of the code.

The script rl_pwr.py contains the main RL algorithm controller, with user defined options for the Q-learning settings.

The script InputGen2.py takes the user defined input from user_input.py and begins setting up SIMULATE .inp files.

The script simulate.py creates directories for each of the SIMULATE jobs and submits them via SLURM to run on the RDFMG cluster.

The script Output_Search.py collects SIMULATE .out files and parses through them for quantities of interest from the SIMULATE calculations.

The script main2.py is a controller that manages the running of user_input.py, InputGen2.py, and simulate.py.

reward_cgm.py contains the "Reward" class for the algorithm, which contains functions that calculate reward from output data.
test_impot.py contains the "RL" class for the q-learning algorithm, which performs the reinforcement learning using the calculated reward.



The directory "Base Files" contains the following needed for the simulation:
	- sample restart (.res) file for SIMULATE-3 
	- a sample input (.inp) file for SIMULATE-3 
	- a sample shell script (.sh) for SLURM 
	- fuel library file (.lib) from CASMO code suite for pre-defined fuel inventory
	
	
Upon running the code in the RDFMG cluster using the command--->  python -i rl_pwr.py > results.txt

The following directories should be created.	
	
	
	- The directory "Queue" contains the SIMULATE input file(s) created by the code, ready for submission via the RDFMG cluster.

	- The directory "SimRuns" contains subdirectories for each of the SIMULATE calculation runs, including copied files from "Base Files" that are required.

	- The directory "Outputs" contains the collected SIMULATE output files from the user specified number of calculations.

