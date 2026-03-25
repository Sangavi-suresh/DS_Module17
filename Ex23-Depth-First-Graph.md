# Ex23 Depth First Graph
## DATE:
## AIM:
To compose the code for the function createNode to traverse the graph below in the depth first fashion.

![image](https://github.com/user-attachments/assets/63552824-d0a3-49c6-a473-6db27d1f03e4)

## Algorithm
1.Start the program
2.Initialize adjacency matrix and visited array
3.Choose a starting vertex
4.Mark the vertex as visited and print it
5.Recursively visit all unvisited adjacent vertices
6.Repeat until all vertices are visited
7.Stop

## Program:
```
/*
Program to traverse graph using DFS
Developed by: SANGAVI S
RegisterNumber:  212222230130
*/

#include<stdio.h>

#define MAX 10

int adj[MAX][MAX], visited[MAX];

// DFS function
void DFS(int v, int n)
{
    int i;

    printf("%d ", v);
    visited[v] = 1;

    for(i = 0; i < n; i++)
    {
        if(adj[v][i] == 1 && visited[i] == 0)
        {
            DFS(i, n);
        }
    }
}

int main()
{
    int n, e, i, j, u, v;

    printf("Enter number of vertices: ");
    scanf("%d", &n);

    printf("Enter number of edges: ");
    scanf("%d", &e);

    // Initialize
    for(i = 0; i < n; i++)
    {
        visited[i] = 0;
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
        adj[v][u] = 1;
    }

    printf("DFS Traversal: ");
    DFS(0, n);

    return 0;
}
```

## Output:
<img width="546" height="481" alt="image" src="https://github.com/user-attachments/assets/192ff5a6-4fce-407d-acad-0fbf08d445fd" />



## Result:
Thus, the C code for the function createNode to traverse the graph below in the depth first fashion is implemented successfully
