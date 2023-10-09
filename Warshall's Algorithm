#include <stdio.h>

#define MAX_VERTICES 10

int max(int a, int b) {
    return (a > b) ? a : b;
}

void warshall(int p[MAX_VERTICES][MAX_VERTICES], int n) {
    int i, j, k;
    for (k = 1; k <= n; k++) {
        for (i = 1; i <= n; i++) {
            for (j = 1; j <= n; j++) {
                p[i][j] = max(p[i][j], p[i][k] && p[k][j]);
            }
        }
    }
}

int main() {
    int p[MAX_VERTICES][MAX_VERTICES] = { 0 };
    int n, e, u, v, i, j;

    printf("Enter the number of vertices: ");
    scanf("%d", &n);
    
    printf("Enter the number of edges: ");
    scanf("%d", &e);

    for (i = 1; i <= e; i++) {
        printf("Enter the end vertices of edge %d: ", i);
        scanf("%d %d", &u, &v);
        p[u][v] = 1;
    }

    printf("\nMatrix of input data:\n");
    for (i = 1; i <= n; i++) {
        for (j = 1; j <= n; j++) {
            printf("%d\t", p[i][j]);
        }
        printf("\n");
    }

    warshall(p, n);

    printf("\nTransitive closure:\n");
    for (i = 1; i <= n; i++) {
        for (j = 1; j <= n; j++) {
            printf("%d\t", p[i][j]);
        }
        printf("\n");
    }

    return 0;
}
