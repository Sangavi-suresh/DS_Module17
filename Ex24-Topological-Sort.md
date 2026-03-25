# Ex24 Topological Sort
## DATE:
## AIM:
To compose the code to determine whether the topological ordering for the following graph is possible or not.

![image](https://github.com/user-attachments/assets/c74a7111-9b59-475c-aad4-9baf23d50ec0)


## Algorithm
1.Start the program
2.Read number of vertices and edges
3.Initialize adjacency matrix and indegree array
4.Calculate indegree of each vertex
5.Insert vertices with indegree 0 into queue
6.Remove vertex from queue, print it, and reduce indegree of adjacent vertices
7.If all vertices are visited → topological order possible
8.Else → cycle exists (not possible)  

## Program:
```
/*
Program to determine topological ordering using Kahn's Algorithm
Developed by:SANGAVI S 
RegisterNumber:212222230130 
*/

#include<stdio.h>

#define MAX 10

int adj[MAX][MAX], indegree[MAX], queue[MAX];

int main()
{
    int n, e, i, j, u, v;
    int front = 0, rear = -1;
    int count = 0;

    printf("Enter number of vertices: ");
    scanf("%d", &n);

    printf("Enter number of edges: ");
    scanf("%d", &e);

    // Initialize
    for(i = 0; i < n; i++)
    {
        indegree[i] = 0;
        for(j = 0; j < n; j++)
            adj[i][j] = 0;
    }

    printf("Enter edges (u v):\n");
    for(i = 0; i < e; i++)
    {
        scanf("%d %d", &u, &v);
        adj[u][v] = 1;
    }

    // Calculate indegree
    for(i = 0; i < n; i++)
    {
        for(j = 0; j < n; j++)
        {
            if(adj[j][i] == 1)
                indegree[i]++;
        }
    }

    // Enqueue vertices with indegree 0
    for(i = 0; i < n; i++)
    {
        if(indegree[i] == 0)
            queue[++rear] = i;
    }

    printf("Topological Order: ");

    while(front <= rear)
    {
        int node = queue[front++];
        printf("%d ", node);
        count++;

        for(i = 0; i < n; i++)
        {
            if(adj[node][i] == 1)
            {
                indegree[i]--;
                if(indegree[i] == 0)
                    queue[++rear] = i;
            }
        }
    }

    // Check for cycle
    if(count != n)
        printf("\nTopological ordering NOT possible (Cycle exists)");
    else
        printf("\nTopological ordering possible");

    return 0;
}
```

## Output:
<img width="487" height="371" alt="image" src="https://github.com/user-attachments/assets/d2226d0f-1f33-4c34-8ca4-3eeca05419c0" />



## Result:
Thus, the C program for determining whether the topological ordering for the following graph is possible or not, is implemented successfully.
