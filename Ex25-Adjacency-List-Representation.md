# Ex25 Adjacency List Representation
## DATE:
## AIM:
To write a C program to represent the given graph using the adjacency list.

## Algorithm
1.Start the program
2.Define structure for node (vertex and next pointer)
3.Create an array of pointers for adjacency list
4.Initialize all list heads to NULL
5.Input edges (u, v)
6.Insert nodes at beginning of list for both vertices (undirected graph)
7.Display adjacency list for each vertex
8.Stop   

## Program:
```
/*
Program to represent graph using adjacency list
Developed by: SANGAVI S
RegisterNumber: 212222230130
*/

#include<stdio.h>
#include<stdlib.h>

struct node
{
    int vertex;
    struct node* next;
};

struct node* adj[10];

// Create new node
struct node* createNode(int v)
{
    struct node* newNode = (struct node*)malloc(sizeof(struct node));
    newNode->vertex = v;
    newNode->next = NULL;
    return newNode;
}

// Add edge (undirected)
void addEdge(int u, int v)
{
    struct node* newNode = createNode(v);
    newNode->next = adj[u];
    adj[u] = newNode;

    newNode = createNode(u);
    newNode->next = adj[v];
    adj[v] = newNode;
}

// Display adjacency list
void display(int n)
{
    int i;
    struct node* temp;

    for(i = 0; i < n; i++)
    {
        printf("Vertex %d: ", i);
        temp = adj[i];
        while(temp)
        {
            printf("%d -> ", temp->vertex);
            temp = temp->next;
        }
        printf("NULL\n");
    }
}

int main()
{
    int n, e, i, u, v;

    printf("Enter number of vertices: ");
    scanf("%d", &n);

    printf("Enter number of edges: ");
    scanf("%d", &e);

    // Initialize
    for(i = 0; i < n; i++)
    {
        adj[i] = NULL;
    }

    printf("Enter edges (u v):\n");
    for(i = 0; i < e; i++)
    {
        scanf("%d %d", &u, &v);
        addEdge(u, v);
    }

    printf("\nAdjacency List:\n");
    display(n);

    return 0;
}
```

## Output:

<img width="413" height="452" alt="image" src="https://github.com/user-attachments/assets/1b2a68d1-87ee-4ccd-889e-54764334e773" />


## Result:
Thus, the C program to represent the given graph using the adjacency list is implemented successfully
