#include <iostream>
#include <vector>
#include <queue>
#include <limits>
#include <unordered_map>
#include <set>
using namespace std;

struct Edge {
    int dest;
    int weight;
};

class Graph {
public:
    Graph(int numFloors) {
        adjacencyList.resize(numFloors + 1);
    }

    void addEdge(int src, int dest, int weight) {
        Edge edge;
        edge.dest = dest;
        edge.weight = weight;
        adjacencyList[src].push_back(edge);
    }

    vector<Edge> getAdjacentFloors(int floor) {
        return adjacencyList[floor];
    }

private:
    vector<vector<Edge>> adjacencyList;
};

int dijkstra(Graph& graph, int start, int end, unordered_map<int, int>& visited) {
    priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>> pq;
    pq.push({0, start});

    while (!pq.empty()) {
        int currentDistance = pq.top().first;
        int currentNode = pq.top().second;
        pq.pop();

        if (visited[currentNode]) {
            continue;
        }

        visited[currentNode] = true;

        if (currentNode == end) {
            return currentDistance;
        }

        vector<Edge> adjacentFloors = graph.getAdjacentFloors(currentNode);
        for (const Edge& edge : adjacentFloors) {
            int dest = edge.dest;
            int weight = edge.weight;

            if (!visited[dest]) {
                pq.push({currentDistance + weight, dest});
            }
        }
    }

    return numeric_limits<int>::max();
}

int main() {
    int numFloors;
    cout << "Enter number of floors in a building: ";
    cin >> numFloors;

    Graph graph(numFloors);

    // Add edges representing the shortest paths between floors
    for (int i = 1; i <= numFloors; ++i) {
        if (i < numFloors) {
            graph.addEdge(i, i + 1, 1);
        }
        if (i > 1) {
            graph.addEdge(i, i - 1, 1);
        }
    }

    int currentFloor;
    cout << "Enter the floor where the elevator is currently located in a building: ";
    cin >> currentFloor;

    int destinationCount;
    cout << "Enter the number of destination floors: ";
    cin >> destinationCount;

    vector<int> destinationFloors(destinationCount);
    cout << "Enter the destination floors: ";
    for (int i = 0; i < destinationCount; ++i) {
        cin >> destinationFloors[i];
    }

    unordered_map<int, int> visited;
    for (int destination : destinationFloors) {
        int shortestPathToDestination = dijkstra(graph, currentFloor, destination, visited);
        cout << "Elevator is moving from floor " << currentFloor << " to floor " << destination << endl;
        currentFloor = destination;
    }

    cout << "Elevator is idle" << endl;

    while (true) {
        cout << "Enter multiple requests from the adjacent floors for current floor "
             << currentFloor << " (enter -1 to finish): ";

        int request;
        set<pair<int, int>> requests; // Pair of (shortest path distance, floor)

        while (cin >> request && request != -1) {
            unordered_map<int, int> visited;
            int shortestPath = dijkstra(graph, currentFloor, request, visited);
            requests.insert({shortestPath, request});
        }

        if (requests.empty()) {
            break;
        }

        int totalDistance = 0;

        for (const auto& req : requests) {
            int nextFloor = req.second;
            int shortestPath = req.first;
            totalDistance += shortestPath;

            cout << "Elevator is moving from floor " << currentFloor
                 << " to floor " << nextFloor << endl;

            currentFloor = nextFloor;
        }
    }

    cout << "Elevator is idle" << endl;

    return 0;
}
