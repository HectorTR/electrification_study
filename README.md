
# ELECTRIFICATION STUDY 

# Background 
The electrification of end-uses in U.S residences and buildings is expected to grow under current policies. Electrification of buildings, transportation and industry will have an impact in the infrastructure and electricity economics. Exploring adoption scenarios and how enegy and electricity consumption patterns might impact the current infrastructure will guide the transition into a decarbonized and sustainable economy. 

A data driven comparative study between electrification categories (building, transportation, and industry) that weights and compiles data of each category will help to determine which category is the greater contributor to infrastructural/retrofits in the grid.  


# Introduction 
The Electrification Study estimates a feeder loading impact relative to electrificationin buildings. The readiness of the system to accomodate that extra load without affecting safety, reliability, and power quality. 

## Electrification Criteria 
In buildings, water heaters and HVAC systems (heating, ventilation, and air conditioners) are the electrification drivers in most cases.

## Under typical operation condition
A entire year was simulated in several climate regions, to obtain Load Duration Curves. Identifying the most energy intense hours of the year, and the amount of energy demanded.

A typical hot summer day was simulated simulated in several climate regions, described the Peak Demand of the feeder and the ocurrence of it. 

## Methodology
Define a number of houses to be connected to each phase of the distribution line.
Define a weather or climate zone. in `data` a library of weather files can be found. 
Define The number of houses that will have AC in the sample. 
Define the electrification baseline and penetration levels, as a percentage of the entire sample. 
Run the model 
Retrieve results


## How the Model Works 
The model runs a power flow simulation and determines the load on a swing bus connected to the bulk grid. The case is configured to run a sensitivy analysis on the effects of appliances electrification, while assuming no mixing of gas and electric appliances per residence. when a residence among the sample is electrified all appliances will be electric, water heater, stove, HVAC system and dryer. 

The representation of thermal integrity of each house (shell) is given by square footage of the residence and its weatherization. For each single family residence models heating, ventilation and air conditioning (HVAC) electricity consumption is based exclusively on occupation, thermostat settings, residence weatherization, and typica load schedules for the climate zone selected. 

# Data Inputs 
## Climate Zone 
The utilization of TMY3 data allows the model to explore typical metheorological conditions, but represents a roadblock if extreme conditions are desired to be modeled. 

## Simulation Configuration and input variables 
To configure the model use file `config/simulation_configuration.csv`.
The types of variables defined in the file are: 
- Number of houses per phase (for a 3 phase circuit)
- Start time of the simulation
- Stop time of the simulation
- Weather location
- Baseline Number of Houses with AC per Phase
- The rest of the file defines the gas fraction: This is done by defining the name of the run and percent electrification (ie percent number of houses that have all electric appliances versus all gas appliances).

Appliances that can defined as gas are: Clothes Dryer, Waterheater, Heating, Stove/Range. If the house is defined to use gas as fuel, the model assumes all the aforementioned appliances are gas.

## Data retrieved from the model
The simulation results for each electrification portion retrieves for the meter in each house measurements of power or energy. The selection will have to be made in the `house object`. 

The recorder that will allo to report each measurement can also be configured to record at a speficic time or when a change is registered. 

## Output
The output from all the defined run in configuration will appear in `output/` folder.
