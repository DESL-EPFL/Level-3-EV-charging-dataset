# EV-charging-data
The data refer to a level 3 electric vehicle (EV) charging station located in south western Switzerland. The data has been measured from April 12th 2022 to July 4th 2023.

The charging station includes 6 charging options: 2xCCS, 1xCHAdeMO, 1xType 2 socket, 1xType 2 plug, and 1xTesla DC charging plug. Only measurements from the CCS plugs are included in the data as the utilization of other charging options were significantly lower. The maximum power of the charging station is 172.5 kW and two EVs can be supplied at the same time. 
In case of two simultaneous charging sessions, the power capacity is divided equally for both. If one EV draws less capacity than the allocated capacity, the otherwise unused capacity is allocated to the other EV.
The data is retrieved by a custom made data acquisition system developed in LabVIEW. The data include measurement data and session data. The measurement data consist of 64277 data points with a 1-minute resolution. The session data consist of 1878 EV charging sessions seen in the measurement data. 
Measurement data
A measurement data point includes the following values: 
•	Data and time
•	CCS		Plug ID (CCS1 or CCS2)
•	Session	ID number given for the session
•	P		AC charging power of the charging station (W)
•	Pset		Power setpoint set by the charging station (W)
•	Preq		Power requested by the EV (W)
•	TotalCapacity	Total energy capacity of the EV’s battery
•	RemainingCapacity	Remaining energy in the EV’s battery
•	BulkCapacity	Usable energy capacity of the EV’s battery
•	Energy	Cumulative energy charged of the charging session (Wh)
•	SOC		State-of-charge of the EV’s battery (%)
•	Ctrl_t		Boolean whether Pset was lower than Preq at the time interval (0=False, 1=True)
•	Ctrl_s		Boolean whether Pset was lower than Preq anytime during the charging session (0=False, 1=True)
Quantities are recorded with one-minute interval.
Session data
Each charging session includes the following values:
•	Session	ID number given for the session
•	CCS		Plug ID (CCS1 or CCS2)
•	Arrival	
•	Departure	
•	Stay 		Stay duration (min)
•	Energy 	Charged energy (Wh)
•	Pmax		Maximum AC charging power of the session (W)
•	Preq_max	Maximum requested power of the session (W)
•	Controlled session 	Boolean whether Pset was lower than Preq anytime during the charging session (0=False, 1=True)	
•	TotalCapacity	Total energy capacity of the EV’s battery
•	BulkCapacity	Usable energy capacity of the EV’s battery
•	SOC arrival	State-of-charge of the EV’s battery at arrival (%)
•	SOC departure	State-of-charge of the EV’s battery at departure (%)
•	Energy capacity 	Approximated capacity of the EV’s battery (Wh)
