# Instructions for the test system PROSPECT-43

## Structure of the file

###  'Profile' sheet

The profile sheet introduces the operational parameters and indices of the test system.

There are 5 types of loads as shown in the following table.

| Load index | Load type                                                    |
| ---------- | ------------------------------------------------------------ |
| 1          | Traditional loads including traditional industrial loads, residential loads etc. |
| 2          | Loads related to 5G infrastructure                           |
| 3          | Loads of data centers                                        |
| 4          | Loads of electrical vehicles                                 |
| 5          | Loads of P2H (hydrogen industry)                             |
| 6          | The total load, namely the sum of load #1 to load #5         |

The system we provide has 43 buses including 40 buses in the main grid and 3 buses in the remote renewable energy (RE) bases.  There are no existing generators and power loads in the RE bases. The detailed information will be introduced in the later sheets.

There are 8 stages in our test system. The interval between two stages is 5 years. Accordingly, the whole planning duration is 35 years representing the power system transition from 2025 to 2060.

We provide 3 types of carbon emission constraints. The first one is indicated by 'Carbon target of all stages '. This parameter represent the overall carbon emission constraint during the whole planning periods. The second one is indicated by 'Carbon target of Stage 8'. This parameter mean the yearly carbon emission constraint in the 8th stage namely 2060. The third one is more elaborate. According to other relevant studies, we introduce a carbon-reduction curve towards the low-carbon target which represents yearly carbon emissions in each stage.  The curve restrain carbon emissions in each stage. 

### 'Bus' sheet

This sheet introduces buses, their belonging regions and their 'load participation factor by region'. The load of a specified bus can be obtained by the participation factor and the regional load curve.  

There are 8 regions in our case: R1 to R5 in the main grid and ER1 to ER3 in the SE province.  ER1 to ER3 represent the energy base in the remote area, and in our case there are no existing generators and loads in these regions.

### 'Lines' sheet

This sheet introduces the information about existing lines and candidate lines.

The existing lines include 500kV and 1000kV AC lines, and the candidate lines include 500kV, 1000kV AC lines and ±800kV DC lines.

The electrical parameters are modeled differently between existing lines and candidate lines. There are physically a number of loops in a single transmission corridor. The parameters of existing AC lines are given in the corridor-based form (equivalent parameters of the parallel of loops), while candidate AC lines' parameters are given in the loop-based form (parameters of the single loop).

As for existing lines, the loops of transmission lines are equivalent to a single line. The resistance, reactance, susceptance parameter in the table are the equivalent parameter of the parallel loops.

As for candidate lines, the parameters ('Resistance R (p.u.)', 'Reactance X (p.u.)', 'Half of Susceptance B/2 (p.u.)', 'Line capacity (MW) ','Line Inv. Cost (10^4 CNY/km)') in the table are given as **a single loop**. Readers should take care when many loops are planned to be invested.

The resistance, reactance, and susceptance in the table are the per unit values. The base power is set as 100 MVA, and the base voltage is set as the line voltage.

### 'Generation Units' sheet

There are 11 types of generation units in this case. 

| Generation index | Generation type                 |
| ---------------- | ------------------------------- |
| 1                | Coal Generator (Large Capacity) |
| 2                | Coal Generator (Small Capacity) |
| 3                | Gas                             |
| 4                | Hydro                           |
| 5                | Nuclear                         |
| 11               | PV (utility)                    |
| 12               | PV (distributed)                |
| 13               | CSP                             |
| 14               | Wind (onshore)                  |
| 15               | Wind (offshore)                 |
| 31               | EG                              |

The capacity of existing and candidate generation units are respectively shown in the 'Existing Units-Overview' and 'Candidate Units-Overview' sheet.

For the convenience of readers , the parameters of generation units are organized in the 'Generation-Parameters', 'Units-Investment Costs' and 'Units-Variable Costs' sheet.

A capacity value of -1 denotes unlimited availability for this unit type.

The investment costs of units decline as the technology progresses, and the variable costs vary across different regions.

The 8760-hour curve of renewable energy is given in the attached files 'vre_PROSPECT43.mat'. The utilization hour of renewable energy is different across regions.

Additionally, an amount of energy is imported from neighboring regions into the main grid in Y1. This energy injection is modeled as a specialized generation unit, referred to as external generators (EGs) in this test system.

### 'Storage Units' sheet

Two types of storage units are considered in the case: the battery and the pumped hydro.

The capacity of existing and candidate storage units are respectively shown in the 'Existing Units-Overview' and 'Candidate Units-Overview' sheet.

For the convenience of readers , the parameters of generation units are organized in the 'Storage-Parameters', 'Units-Investment Costs' and 'Units-Variable Costs' sheet.



### 'Load_YearMax' & 'Load_YearSum' sheet

The penetration of new-type loads is increasing as the ICT technology develops and new-type loads usually have special characteristics and are promising to engage in multiple power-system-operation programs. As a result, we further divide loads into 5 types: traditional loads, 5G loads, data center, EV, P2H.

 

The 8760-hour load curve is given in the attached file  'load_PROSPECT43.mat'. The max load power (MW) and yearly energy consumption (MWh) during stage 1 to stage 8 are given in the 'Load_YearMax' & 'Load_YearSum' sheet respectively.



