# Solving EVRP with backhauls and time windows under the uncertainties of travel time and service time

Author: Dongbo Peng ([dpeng017@ucr.edu](mailto:dpeng017@ucr.edu))

#### 1.1 EVRPBTW-USUT Benchmark Dataset Description

To examine the proposed electric vehicle routing problem with backhauls and time windows under travel time and service time uncertainty (EVRPBTW-USUT), we introduce a new EVRPBTW benchmark dataset based on the well-known EVRPTW benchmark instances introduced by Schneider et al. (Schneider et al., 2014). Our EVRPBTW benchmark dataset incorporates a backhaul strategy for a battery electric vehicle (BEV) fleet, reflecting a practical application in urban logistics and supply chain services. Customers are divided into two groups: linehaul customers (L), who require deliveries, and backhaul customers (L), who require pickups.

We selected 10 instances from the EVRPTW benchmark dataset, where the customers are randomly distributed in the hypothesis scenario. For each instance, similar to (Toth \& Vigo, 1997), we generate two EVRPBTW instances based on one EVRPTW dataset, each corresponding to an approximate linehaul percentage of 66% and 75%, respectively. Backhaul customers are grouped in sets of two, three, or four. Other aspects, such as customer locations, time windows, recharging stations, and EV characteristics, remain unchanged. Therefore, for each EVRPTW benchmark dataset, we can generate two new EVRPBTW instances.

For example, the instance named “r201\_C25B3” represents a case with 25 customers, where 13 are linehaul customers and 12 are backhaul customers, accounting for approximately 66% backhaul customers. This instance includes 21 recharging stations. In total, 60 instances are generated. The full set of instances can be found in the problem instance files.

In each EVRPBTW instance, it contains the following features:
{'ID': customer ID, 'Type': service type ('D', 'S', 'L', 'B' denote depot, charging station, linehaul customer and backhaul customer, respectively), 'x': x coordinate, 'y': y coordinate, 'demand': customer demand, 'ReadyTime': earliest service start time, 'DueTime': latest service start time, 'ServiceTime': nominal service time}.ßß

For the problem instance parameters, we follow the original problem assumption in (Schneider et al., 2014). For example:
Q: Vehicle fuel tank capacity
C: Vehicle load capacity
r: fuel consumption rate
g: inverse refueling rate
v: average Velocity

#### 1.2 Structure of the benchmark datasets.

The new EVRPTWB benchmark dataset contains 60 instances, with 20 instances including 25 customers, 20 instances including 50 customers, and 20 instances including 100 customers. The instances are provided as CSV files. We store the problem instances and detailed solutions in the compressed ZIP file, named "Section\_3\_2\_EVRPBTW\_benchmark\_instances". The structure of the compressed ZIP file is shown as follow:

--> Section\_3\_2\_EVRPBTW\_benchmark
--> C25B3
--> r201\_C25B3.csv
--> r202\_C25B3.csv
--> ...
--> C25B4
--> C50B3
--> C50B4



1.3 Real-world dispatching dataset.
The real-world dispatching data is stored in "realcase\_dataset", which includes a CSV file for an instance with 47 customers. There are three types of CSV files:
Problem instance: Section3\_real\_case\_data.csv
Distance matrix: real\_case\_distance\_matrix.csv
Time matrix: real\_case\_time\_matrix.csv

This Excel file "Section\_3\_3\_Real\_case\_solutions.xlsx" provides a comparison of two vehicle routing solutions generated for the same transportation network. Each solution consists of a set of routes originating and ending at a central depot (node 0). The routing results are listed under:

Det\_sol: The routing solution obtained from a deterministic model, where travel times, service times, and other parameters are assumed to be known and fixed.
Rob\_sol: The routing solution obtained from a robust optimization model, which accounts for uncertainty in travel and service times to enhance solution reliability.
Each solution is represented as a list of routes, with each route defined as a sequence of node IDs. All routes start and end at node 0, which denotes the depot.



References:
Schneider, M., Stenger, A., \& Goeke, D. (2014). The electric vehicle-routing problem with time windows and recharging stations. Transportation Science, 48(4), 500–520.


