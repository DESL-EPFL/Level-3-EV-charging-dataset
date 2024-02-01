# Level 3 electric vehicle charging dataset
## Description of the commercial EV charging station used to collect the dataset

The dataset has been collected on a level 3 electric vehicle (EV) charging station located in southwestern Switzerland. The data has been measured from April 12th 2022 to July 4th 2023.

The charging station includes 6 charging plugs: 2xCCS, 1xCHAdeMO, 1xType 2 socket, 1xType 2plug, and 1xTesla DC. Only measurements from the CCS plugs are included in the dataset as the utilization of other charging options were significantly lower. The maximum power of the charging station is 172.5 kW and two EVs can be supplied at the same time.

In case of two simultaneous charging sessions, the power capacity is equally divided however, in case one EV draws less power than the allocated one by the charging station, the otherwise unused capacity is allocated to the other EV.

The data is retrieved by a custom-made data acquisition software developed by the EPFL-DESL. The data include measurement and session data. The measurement dataset consist of 64277 measurements with a 1-minute resolution. The session dataset consists of 1878 EV charging sessions contained in the measurement data. The description of the two dataset is reported here below.

## Measurement dataset
A measurement data point includes the following values:
| Identifier | Description |
| --- | --- |
| _Data and time_ | |
| _CCS_ | Plug ID (CCS1 or CCS2) |
| _Session_ | ID number given for the session |
| _P_ | AC charging power of the charging station [W] |
| _Pset_ | Power setpoint set by the charging station [W] |
| _Preq_ | Power requested by the EV [W] |
| _TotalCapacity_ | Total energy capacity of the EV’s battery |
| _RemainingCapacity_ | Remaining energy in the EV’s battery |
| _BulkCapacity_ | Usable energy capacity of the EV’s battery |
| _Energy_ | Cumulative energy charged of the charging session [Wh] |
| _SOC_ | State-of-charge of the EV’s battery [%] |
| _Ctrl_t_ | Boolean identifying whether Pset < Preq at the time interval (0=False, 1=True) |
| _Ctrl_s_ | Boolean identifying whether Pset < Preq anytime during the charging session (0=False, 1=True) |

Quantities are recorded with a sampling time of one minute.

## Session data
Each charging session includes the following values:
| Identifier | Description |
| --- | --- |
| _Session_ | ID number attributed to the charging session |
| _CCS_ | Plug ID (CCS1 or CCS2) |
| _Arrival_ | EV arrival time |
| _Departure_ | EV departure time |
| _Stay_ | EV stay duration [min] |
| _Energy_ | Charged energy [Wh] |
| _Pmax_ | Maximum AC charging power of the session [W] |
| _Preq_max_ | Maximum AC charging power of the session [W] |
| _Controlled session_ | Boolean identifying whether Pset < Preq anytime during the charging session (0=False, 1=True) |
| _TotalCapacity_ | Total energy capacity of the EV’s battery [a-dimensional] |
| _BulkCapacity_ | Usable energy capacity of the EV’s battery [a-dimensional] |
| _SOC arrival_ | State-of-charge of the EV’s battery at arrival [%] |
| _SOC departure_ | State-of-charge of the EV’s battery at departure [%] |
| _Energy capacity_ | Approximated capacity of the EV’s battery [Wh] |
