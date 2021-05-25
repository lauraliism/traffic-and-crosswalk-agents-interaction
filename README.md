# Modelling Interactions Between Traffic and Crosswalk Agents at Unsignalized Crossings

This is the code used for investigating vehicle-bicycle interactions at unsignalized crossings. The research and results are elaborated in more depth in my Master's Thesis "Modelling Interactions Between Traffic and Crosswalk Agents at Unsignalized Crossings" (link will soon be added).

High level work process: 
* Investigating vehicle and bicycle trajectories  
    - Quality of data (time, distance etc between data points)
    - Plotting trajectories etc.
* Defining the Conflict Zone (CZ) based on trajectories intersection area  
* Coupling vehicle and bicycle trajectories that were simultaneously in the CZ
    - Generating videos of such possible interactions
    - Defining the vehicle and bicycle Interaction Zones (IZ)
    - Discarding some possible interactions that were too short
    - Manually labelling possible interactions based on generated videos
* Generating features such as:
    - _"timeOfEnteringInteractionZone"_
    - _"speedAtTheBorderOfInteractionZone"_
    - _"minSpeedInsideInteractionZone"_ 
    - _"arrivalTimeDifference"_ (ATD)
    - _"speedWhenOtherAgentEnteredIZ"_
    - _"minSpeedDistance"_
* Investigating possible interactions
    - Estimating conflict probability using logistic regression model and labelled interactions
    - Defining conflict events using ATD range of -2.5 to +5 seconds (identified by estimating conflict probability)
    - Dividing data into conflict, non-conflict, yield and non-yield groups (ATD of -2.5 to +5 seconds identified to separate conflict events by estimating conflict probability)
    - Plotting data relative to different features and different event groups
    - Selecting features using _f_regression_
    - Estimating yielding probability using logistic regression model and different combinations of selected features
