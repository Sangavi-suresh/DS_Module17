# Ex21 Representation of Graph
## DATE:
## AIM:
To write a C program to display the adjacency matrix of the given graph by supplying the edges and the number of vertices.

## Algorithm
1.Start the program
2.Read number of vertices n and edges e
3.Initialize adjacency matrix with 0
4.Input edges (u, v)
5.Set adj[u][v] = 1 and adj[v][u] = 1 (for undirected graph)
6.Display adjacency matrix
7.Stop   

## Program:
```
/*
Program to display adjacency matrix of a graph
Developed by: SANGAVI S
RegisterNumber: 212222230130 
*/

#include<stdio.h>

int main()
{
    int adj[10][10], n, e, i, j, u, v;

    printf("Enter number of vertices: ");
    scanf("%d", &n);

    printf("Enter number of edges: ");
    scanf("%d", &e);

    // Initialize matrix
    for(i = 0; i < n; i++)
    {
        for(j = 0; j < n; j++)
        {
            adj[i][j] = 0;
        }
    }

    // Input edges
    printf("Enter edges (u v):\n");
    for(i = 0; i < e; i++)
    {
        scanf("%d %d", &u, &v);
        adj[u][v] = 1;
        adj[v][u] = 1; // Undirected graph
    }

    // Display matrix
    printf("\nAdjacency Matrix:\n");
    for(i = 0; i < n; i++)
    {
        for(j = 0; j < n; j++)
        {
            printf("%d ", adj[i][j]);
        }
        printf("\n");
    }

    return 0;
}
```

## Output:
<img width="397" height="455" alt="image" src="https://github.com/user-attachments/assets/a61c2f2e-aacc-493a-95c5-0a2f43cf17c4" />



## Result:
Thus, the C program to print the adjacency matrix of the given graph is implemented successfully.
