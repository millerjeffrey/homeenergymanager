# homeenergymanager
# homeenergymanager is a set of tools to manage peak power utilization and/or minimize costs under variable rate plans.  The goal is to gather cost data, along with current usage data and then use that data to control the loads like EVSE, HVAC, Freezers.  Someday I hope we have a single interface for the home to show and manage where the energy is going and how much it is costing us.  


## External data collection modules
### #goals
####To round up relevant data both real time and forecasts of price and demand.  This could also include weather forecasts including solar loading.  These are all very specific to the region, however the weather in a specific location isn't that relevant, more the weather in a whole region.  The regions of relevance are determined by the region covered by the electrical market.  Could also include direct data feeds from provider via SMS or other inputs formats that they support in regards to peak loads, rolling blackouts, etc.

## Prediction modules
### goals
#### To take the input data above, run that against the pricing rules of the region to come up with a simple output of the following four states based on cost points set by the user considering both peak demand days in COMED land, or simpler current cost model: 
1. Maximum consumption (charge batteries, precool/preheat, run laundry, wash dishes, run computational intensive processes, and anything else)
2. Steady state (hold temperature steady/very slowly move cheaper, keeping temp within normal setpoint, finish up energy intensive processes)
3. Small reduction (Let temperature drift a bit faster to the cheap and allow to get slightly above set point by 0.X degrees per hour, cut car charging off completely along with all other large loads that can be time shifted)
4. Drastic reduction (everything non-critical is off or severely restricted, draw from batteries to net zero draw from grid if available)  




Internal data collection modules
#goals
Collect data on interior temp, refrigerator temp, power being drawn by charging stations, total power being drawn by house, total energy drawn by car since last connection to compare with expected behavior to estimate completion times.  

Action modules
#goals
Modules needed to take each of the above actions. 
Includes conditions around how long things can be paused for.  Example, you probably don't want your refrigerator off for the whole day and have your food go bad.  

Load Balancing modules
#goals
Under some electricity agreements the provider puts a KW cap on the service.  For others we might draw so much that we approach the limits of the service to the house or a certain panel.  If the data is available we can trim loads to maintain various limits.  Uses the same action modules to manage load.  

Data display modules
#goals
Display what is going on and provide overrides for various functions.  Example I really need to go someplace and need to charge the car.  

