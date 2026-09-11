Assignment 4: Dijkstra's Algorithm
This folder contains the implementation, test output, and complete documentation for Assignment No. 4: Smart City Emergency Response System using Dijkstra's Algorithm.

Problem Overview
In a smart city infrastructure, ambulances must navigate road networks to reach the nearest hospital in the minimum possible travel time. Road networks are modeled as weighted graphs 
G
=
(
V
,
E
)
, where intersections represent vertices and edges represent roads with weights indicating real-time travel times based on traffic congestion.

Using Dijkstra's Algorithm with a priority queue (min-heap), the system dynamically computes the shortest travel-time path from the ambulance's initial location (source node 
S
) to the nearest hospital in 
O
(
(
V
+
E
)
log
⁡
V
)
 time complexity, and adapts to real-time traffic updates.

Contents of this Folder
File	Description
nearest_hospital_dijkstra.cpp	Complete C++ implementation of Dijkstra's algorithm for nearest hospital routing
output.png	Terminal execution output screenshot showing shortest travel time and optimal routing
124B1F155_DAA_Assignment_4_Dijkstra_Algorithm.pdf	Complete lab report document formatted in institutional standard (PDF)
