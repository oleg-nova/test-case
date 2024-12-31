# About this role


This role performs the following actions:
1. Checks if the /dev/cpu_dma_latency file exists to globally disable C-states.
1. Disables C-states globally if the file exists.
1. Disables C-states for each CPU individually.
1. Installs the cpupower utility for additional control over C-states.
1. Uses cpupower to disable C-states.
1. Checks and displays the status of C-states after operations are performed.
   
The role handles errors and provides informative messages about task completion. 
Once the role is executed, C-states will be disabled on all available host CPUs.

# Run instructions

# Test/validation instructions

Use [turbostat](https://manpages.debian.org/testing/linux-cpupower/turbostat.8.en.html) for report CPUs frequency and idle statistics







