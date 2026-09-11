# Assignment 4: Smart City Emergency Response System Using Dijkstra's Algorithm

## 📌 Assignment Overview

This assignment implements **Dijkstra's Shortest Path Algorithm** to develop a Smart City Emergency Response System.

In a smart city infrastructure, ambulances need to travel through a network of roads to reach hospitals as quickly as possible. The road network is represented as a **weighted graph**, where:

* **Vertices (V)** represent intersections or locations.
* **Edges (E)** represent roads connecting two locations.
* **Edge weights** represent the estimated travel time between locations.
* The **source node (S)** represents the ambulance's current location.
* Hospital nodes represent possible destinations.

The objective of the system is to determine the **nearest hospital in terms of minimum travel time** and provide the shortest route from the ambulance's current location to that hospital.

---

## 🎯 Problem Statement

Given a weighted graph representing a city's road network, find the shortest travel-time path from an ambulance's initial location to the nearest hospital.

The system uses **Dijkstra's Algorithm with a Priority Queue (Min-Heap)** to efficiently calculate the shortest distance from the source node to all reachable locations.

The hospital having the minimum calculated travel time is selected as the nearest hospital.

---

## 🧠 Algorithm Used

### Dijkstra's Algorithm

Dijkstra's Algorithm is a greedy shortest-path algorithm used to find the minimum distance from a single source vertex to all other vertices in a weighted graph.

It works effectively when all edge weights are **non-negative**.

### Working Steps

1. Initialize the distance of every vertex to infinity.
2. Set the distance of the source vertex to `0`.
3. Insert the source vertex into a **Min-Heap Priority Queue**.
4. Extract the vertex with the smallest known distance.
5. Examine all adjacent vertices.
6. Calculate the new possible distance through the current vertex.
7. If the new distance is smaller than the previously stored distance:

   * Update the distance.
   * Store the parent/predecessor.
   * Insert the updated vertex into the priority queue.
8. Continue until all required vertices have been processed.
9. Compare the shortest distances of all hospital nodes.
10. Select the hospital with the minimum travel time.
11. Reconstruct and display the optimal route using the parent information.

---

## 🏙️ Smart City Application

The algorithm can be applied to an emergency response system where ambulances need to reach hospitals as quickly as possible.

For example:

```text
Ambulance
    |
    S
   / \
  4   2
 /     \
A       B
|       |
3       5
|       |
C-------D
    |
 Hospital
```

Each road has a different travel time. Dijkstra's Algorithm evaluates the available routes and determines the path with the minimum total travel time.

This approach can help emergency services:

* 🚑 Find the fastest route for ambulances.
* 🏥 Identify the nearest hospital.
* 🚦 Consider different travel times on roads.
* 🗺️ Navigate large road networks efficiently.
* 🔄 Recalculate routes when traffic conditions change.

---

## 💻 Implementation Details

The program is implemented in **C++**.

### Main Data Structures

#### 1. Graph

The road network is represented using an **adjacency list**.

Each edge stores:

* Destination vertex
* Travel time/weight

#### 2. Distance Array

The `dist[]` array stores the shortest known travel time from the source node to every vertex.

Initially:

```text
dist[source] = 0
dist[all other vertices] = INF
```

#### 3. Parent Array

The `parent[]` array stores the previous vertex on the shortest path.

It is used to reconstruct the final route from the selected hospital back to the ambulance's starting location.

#### 4. Priority Queue

A C++ priority queue is used as a **Min-Heap**.

The vertex with the smallest current distance is processed first.

This improves the efficiency of Dijkstra's Algorithm compared with repeatedly searching through all vertices for the minimum distance.

---

## ⚙️ Time Complexity

Using an adjacency list and a priority queue/min-heap, Dijkstra's Algorithm has a time complexity of:

```text
O((V + E) log V)
```

Where:

* `V` = number of vertices
* `E` = number of edges

### Space Complexity

The space complexity is:

```text
O(V + E)
```

The adjacency list requires `O(V + E)` space, while the distance, parent, and priority queue structures require additional space proportional to the graph size.

---

## 📂 Files in This Folder

| File                            | Description                                                                                       |
| ------------------------------- | ------------------------------------------------------------------------------------------------- |
| `nearest_hospital_dijkstra.cpp` | Complete C++ implementation of Dijkstra's Algorithm for finding the nearest hospital              |
| `output.png`                    | Screenshot of the terminal execution showing the shortest travel time and optimal route           |
| `README.md`                     | Complete documentation explaining the problem, algorithm, implementation, complexity, and results |

---

## ▶️ How to Compile and Run

### Using g++

Open a terminal in the Assignment 4 directory.

Compile the program using:

```bash
g++ nearest_hospital_dijkstra.cpp -o nearest_hospital_dijkstra
```

Run the program using:

### Windows

```bash
.\nearest_hospital_dijkstra.exe
```

### Linux/macOS

```bash
./nearest_hospital_dijkstra
```

---

## 📊 Program Output

The program displays the calculated shortest travel time and the optimal route to the nearest hospital.

Example format:

```text
Shortest travel time to nearest hospital: XX
Optimal Route: S -> ... -> Hospital
```

The actual output depends on the graph and edge weights provided in the program.

The terminal execution screenshot is included in:

```text
output.png
```

---

## 📸 Output Screenshot

The `output.png` file contains the terminal execution result of the program.

It demonstrates that the implemented Dijkstra's Algorithm successfully:

1. Calculates shortest travel times.
2. Identifies the nearest hospital.
3. Determines the minimum-time route.
4. Displays the optimal path.

---

## 🔄 Real-Time Traffic Adaptation

In a real-world Smart City system, road weights can change according to traffic conditions.

For example:

```text
Normal Traffic:
A → B = 5 minutes

Heavy Traffic:
A → B = 15 minutes
```

When traffic conditions change, the corresponding edge weights can be updated and Dijkstra's Algorithm can be executed again to calculate a new optimal route.

This allows the emergency response system to adapt to changing road conditions.

---

## ✅ Advantages

* Efficient shortest-path computation.
* Works well with weighted road networks.
* Priority queue improves performance.
* Can identify the nearest hospital based on travel time.
* Can reconstruct the complete optimal route.
* Suitable for emergency-response applications.
* Can be adapted to changing traffic conditions.

---

## ⚠️ Limitations

* Standard Dijkstra's Algorithm does not support negative edge weights.
* Re-running the algorithm may be required when road weights change significantly.
* Real-world traffic prediction requires additional data sources.
* The basic implementation assumes that the provided travel-time weights accurately represent road conditions.

---

## 🧪 Testing

The implementation was tested using the sample smart-city road network defined in the C++ program.

The test verifies:

* Correct initialization of distances.
* Correct priority queue processing.
* Correct shortest-distance calculation.
* Correct hospital selection.
* Correct path reconstruction.
* Correct terminal output.

The resulting execution is captured in `output.png`.

---

## 📌 Conclusion

The **Smart City Emergency Response System** demonstrates how Dijkstra's Algorithm can be applied to a practical real-world problem.

By representing intersections as vertices and roads as weighted edges, the system can calculate the minimum travel time from an ambulance's current location to different hospitals. The hospital with the smallest shortest-path distance is selected as the nearest hospital.

Using a **priority queue/min-heap** makes the implementation efficient, achieving a time complexity of **O((V + E) log V)**.

The concept can be extended to real-world emergency response systems by dynamically updating road weights according to traffic conditions and repeatedly calculating the optimal route.

Thus, Dijkstra's Algorithm provides an effective foundation for **fast, reliable, and efficient emergency vehicle routing in smart cities**.

---

## 👨‍💻 Assignment Information

**Assignment No.:** 4
**Topic:** Dijkstra's Algorithm
**Application:** Smart City Emergency Response System
**Language:** C++
**Algorithm:** Dijkstra's Shortest Path Algorithm
**Data Structure:** Graph + Priority Queue (Min-Heap)
