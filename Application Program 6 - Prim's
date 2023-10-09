#include <stdio.h>
#include <stdbool.h>
#include <limits.h>

#define MAX_LOCATIONS 100

struct Graph {
    int vertices;
    int adjacency[MAX_LOCATIONS][MAX_LOCATIONS];
};

void initGraph(struct Graph *g, int v) {
    g->vertices = v;
    for (int i = 0; i < MAX_LOCATIONS; i++) {
        for (int j = 0; j < MAX_LOCATIONS; j++) {
            g->adjacency[i][j] = 0;
        }
    }
}

void addEdge(struct Graph *g, int u, int v, int weight) {
    g->adjacency[u][v] = weight;
    g->adjacency[v][u] = weight;
}

void primMST(struct Graph *g) {
    int parent[MAX_LOCATIONS];
    int key[MAX_LOCATIONS];
    bool mstSet[MAX_LOCATIONS];

    for (int i = 0; i < g->vertices; i++) {
        key[i] = INT_MAX;
        mstSet[i] = false;
    }

    key[0] = 0;
    parent[0] = -1;

    for (int count = 0; count < g->vertices - 1; count++) {
        int u, minKey = INT_MAX;
        for (int v = 0; v < g->vertices; v++) {
            if (!mstSet[v] && key[v] < minKey) {
                minKey = key[v];
                u = v;
            }
        }

        mstSet[u] = true;

        for (int v = 0; v < g->vertices; v++) {
            if (g->adjacency[u][v] && !mstSet[v] && g->adjacency[u][v] < key[v]) {
                parent[v] = u;
                key[v] = g->adjacency[u][v];
            }
        }
    }

    printf("Minimum Spanning Tree (MST) edges:\n");
    for (int i = 1; i < g->vertices; i++) {
        printf("%d - %d\n", parent[i], i);
    }
}

int main() {
    struct Graph graph;
    int locations, connections;
    printf("Enter the number of locations: ");
    scanf("%d", &locations);
    initGraph(&graph, locations);

    printf("Enter the number of connections: ");
    scanf("%d", &connections);

    printf("Enter the connections (location1 location2 weight):\n");
    for (int i = 0; i < connections; i++) {
        int loc1, loc2, weight;
        scanf("%d %d %d", &loc1, &loc2, &weight);
        addEdge(&graph, loc1, loc2, weight);
    }

    primMST(&graph);

    return 0;
}
Enter the number of locations: 3
Enter the number of connections: 3
Enter the connections (location1 location2 weight):
0 1 3
1 2 5
0 2 4
Minimum Spanning Tree (MST) edges:
0 - 1
0 - 2
