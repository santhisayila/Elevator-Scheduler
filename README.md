📌 Project Overview
The Elevator Scheduler is a C++ program that simulates the functioning of an elevator inside a multi-floor building. It uses Dijkstra's Algorithm to calculate the shortest path between floors and efficiently manage elevator movement based on user requests.
This project demonstrates the use of graphs, priority queues, adjacency lists, and shortest-path algorithms in a real-time application.

🚀 Features
- Allows the user to specify:
  - Number of floors in the building
  - Current elevator position
  - Multiple destination floors
- Uses Graph Representation to model building floors
- Implements Dijkstra’s algorithm to determine shortest travel paths
- Handles multiple user requests dynamically
- Shows elevator movement from floor to floor
- Continues processing requests until users choose to stop

🧠 Technologies & Concepts Used
- C++
- Graphs & Adjacency Lists
- Dijkstra’s Algorithm
- Priority Queue (Min-Heap)
- STL Containers: vector, queue, unordered_map, set
- Shortest Path Computation
- User Input Handling

📁 Project Structure
ElevatorScheduler/
 ├── elevator.cpp        # Main source code
 ├── README.md           # Documentation
 └── (optional) screenshots/  # Output sample images

🧱 How the System Works
1. Graph is created with edges between adjacent floors.
2. User inputs:
   - Total number of floors
   - Current elevator floor
   - Destination floors
3. Elevator moves to all initial destination floors.
4. Program then enters a loop to accept multiple new requests:
   - Each request is processed using Dijkstra
   - Requests are sorted based on shortest path
   - Elevator moves in optimal order
5. The loop ends when user enters -1.

🔧 How to Compile & Run
Using g++
g++ elevator.cpp -o elevator
./elevator

Using CodeBlocks / Visual Studio
- Create a new C++ project
- Copy the code into main.cpp
- Build & run the project

📌 Sample Input Flow
Enter number of floors in a building: 10
Enter the floor where the elevator is currently located: 3
Enter number of destination floors: 2
Enter the destination floors: 7 2

Multiple Requests Mode:
Enter multiple requests for current floor 2 (enter -1 to finish):
5 9 1 -1

📝 Output Example
Elevator is moving from floor 3 to floor 7
Elevator is moving from floor 7 to floor 2
Elevator is idle

Enter multiple requests...
Elevator is moving from floor 2 to floor 1
Elevator is moving from floor 1 to floor 5
Elevator is moving from floor 5 to floor 9
Elevator is idle

📷 Screenshots
Add screenshots in the /screenshots folder if required:
- 5-floor building example
- 8-floor building example
- 10-floor building example
- 15-floor building example

📚 References
- Dijkstra's Algorithm – GeeksForGeeks
- C++ STL Documentation – cppreference.com, cplusplus.com
- “Introduction to Algorithms” – Cormen
- “Data Structures and Algorithms in C++” – Adam Drozdek

👥 Team Members
- Sk. Ruksana
- S. Thanu Sri
- T. Hema Harshitha
- V. Keerthi Reddy
- S. Santhi Deepika

🏫 Guide
Dr. K Jyothsna Devi, Assistant Professor
Prasad V Potluri Siddhartha Institute of Technology
