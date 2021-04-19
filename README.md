# Data Analysis

ATTENTION: work in progress, this documentation is not complete.

Data analysis in REST in handled through configuration files.
In this repository there are three rml files:
- rawToSignal.rml: it contains the list of processes needed to analyze the acquired data up to the signal analysis (first part of the analysis);
- signalToTrack.rml: it contains the list of processes needed for the track reconstruction (second part of the analysis);
- processes.rml: it contains the specifications (parameters, cuts, …) of the processes involved and listed in rawToSignal.rml and signalToTrack.rml;

and two xml files:
- globals.xml: it contains the global variables shared among all the processes (the global variables are called in the other files with the sintax ${VARIABLE_NAME});
- run.xml: it instantiates a TRestRun object that manages the input and output files among the whole framework.


The analysis is lunched by the following command:
restManager --c CONFIG_FILE --f INPUT_FILE

rawToSignal.rml takes as input a raw datafile; 
signalToTrack.rml takes as input the output of rawToSignal.rml (a root file).

NOTES:
The global.xml and run.xml files could be integrated directly in the rml files, but to simplify the management and for a clener organization it is preferable to keep them separated.

The full list of processes can be found here:

https://github.com/rest-for-physics/framework/blob/master/doc/Chapters/appendix.md#list-of-rest-processes

Extensive REST documentation can be found here:
https://github.com/rest-for-physics/framework/blob/master/doc/Chapters/0-contents.md
