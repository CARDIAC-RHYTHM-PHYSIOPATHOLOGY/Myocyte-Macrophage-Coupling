AVNMacromodel_new.m ODE code Atrio-Ventricular (AVN) mouse model with different macrophage type coupled.

script_AVNMacro.m script to execute ODE code with specific simulations protocol.


ScriptAnalyseParametrePAModelNAVMacro.m analysis code ,parameters extraction follows :
APD90,
Max AP,
Threshold.

odewbar.m progression bar

Recher_Start_Stop.m algorithm search for threshold AP.

main_1D_Macromodel main script to launch the PDE AVN mouse model

AVNmodel_Macromodel_1D.m PDE code Matlab Atrio-Ventricular mouse model chain of 24 cells

A c++ code has been created by Mike Colman and David Conesa Ortega , University of Leeds, UK, based on the Matlab AVN 1D Macromodel in order to handle more than coupled 100 cells
un Instruction.txt file contains the following , to compile

Compile:

    g++ -g -O3 -std=c++11 main_Mangoni1D.cpp -o mangoni.o

Optional arguments to control parameters:

    initial_condition_default  ---- "On"/"Off"          ---- If initial condition are defaulted (On) or they need an input file (initial_conditions.csv)
    
    BCL                        ---- double (ms)         ---- Basic Cycle Length
    
    Ncells                     ---- int                 ---- Number of myocytes
    
    Phi_type/Macrophage_type   ---- int (0, 1, 2, 12)   ---- Type of macrophage (different currents)
    
    Macrophage_coupling        ---- "On"/"Off"          ---- Activate/deactivate coupling with macrophage
    
    Total_time                 ---- double (ms)         ---- Total simulation time
    
    Ncells_stim                ---- int                 ---- Number of stimulated myocytes (the Ncells_stim first)
    
    dcells_Macrophage          ---- int                 ---- Macrophage coupling every dcells_Macrophage cells
    
    Ggap_scale                 ---- float               ---- Scales the strength of adjacent myocytes coupling
    
    Ggapm_scale                ---- float               ---- Scales the strength of coupling with macrophage
    
    Reference                  ---- const char          ---- Folder to store output in
    
    N_Phi			           ---- int 		        ---- Number of Macrophages coupled to myocyte
    

Example:

    ./mangoni.out Ncells 100 dcells_Macrophage 10 Ggap_scale 10 Ggapm_scale 10 Total_time 1000 Macrophage_coupling On Reference Test_10_10

Source files are main_Mangoni1D.cpp,functions_Mangoni1D.cpp,Structs.h
value of initials state in initial_conditions.csv 
