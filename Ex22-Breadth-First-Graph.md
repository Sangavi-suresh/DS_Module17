# Ex22 Breadth First Graph
## DATE:
## AIM:
To write a printQueue C function of the given graph that is to be traversed in the breadth first manner.

![image](https://github.com/user-attachments/assets/f483f48c-6af0-4027-a993-01c108a50933)


## Algorithm
1. Start the program
2.Initialize adjacency matrix and visited array
3.Create a queue for BFS
4.Insert starting vertex into queue and mark it visited
5.While queue is not empty:
6.Remove vertex from queue
7.Display it
8.Add all unvisited adjacent vertices to queue
9.Repeat until all vertices are visited
10.Stop   

## Program:
```
/*
Program to traverse graph using BFS
Developed by: SANGAVI S
RegisterNumber: 212222230130
*/

#include<stdio.h>

#define MAX 10

int adj[MAX][MAX], visited[MAX];
int queue[MAX];
int front = -1, rear = -1;

// Enqueue
void enqueue(int v)
{
    if(rear == MAX - 1)
        return;
    if(front == -1)
        front = 0;
    queue[++rear] = v;
}

// Dequeue
int dequeue()
{
    return queue[front++];
}

// BFS function
void BFS(int n, int start)
{
    int i, v;

    enqueue(start);
    visited[start] = 1;

    while(front <= rear)
    {
        v = dequeue();
        printf("%d ", v);

        for(i = 0; i < n; i++)
        {
            if(adj[v][i] == 1 && visited[i] == 0)
            {
                enqueue(i);
                visited[i] = 1;
            }
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
            adj[i][j] = 0;
    }

    printf("Enter edges (u v):\n");
    for(i = 0; i < e; i++)
    {
        scanf("%d %d", &u, &v);
        adj[u][v] = 1;
        adj[v][u] = 1;
    }

    printf("BFS Traversal: ");
    BFS(n, 0);

    return 0;
}
```

## Output:
<img width="449" height="339" alt="image" src="https://github.com/user-attachments/assets/f989c294-600b-4b55-86a7-e163fd45eee3" />



## Result:
Thus, the code for the printQueue function of the following graph that is to be traversed in the breadth first manner is implemented successfully.
