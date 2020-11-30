---
layout: post
title: Graphs,graphs everywhere - 2
date: 2020-11-30 10:01:00 +0530
permalink: /:title
---

Last time we implemented a graph as a adjacency matrix. Let's look at the more common `adjacency list` method.

An adjancency list is a data structure to represent a graph as a collection of nodes. The structure is very much similar to that of a linked list (and that's because we use linked list to implement this adjacency list. **TLDR**; Linked list === Adjacency list === list, get it?)

On second thoughts, an adjacency list can also be implemented as a collection of map data structure. More on maps [here](https://damercy.github.io/compute/Treasure-maps).


#### The code

```java
  import java.util.*;
  class Graph{
    private int vertices;
    private LinkedList<Integer> adjList[];

    Graph(int vertices){
      this.vertices = vertices;
      adjList = new LinkedList[vertices]; //Array of linked list
      for(int i=0;i<vertices;i++)
        adjList[i] = new LinkedList<>();
    }

    public void addEdge(int u,int v){
      adjList[u].add(v);
      adjList[v].add(u);  // assuming bidirectional edge
    }

    public void showGraph(){
      for(int i=0;i<vertices;i++){
        System.out.print(i+":");
        for(Integer neighbour: adjList[i])
          System.out.print(neighbour+"--->");
        System.out.println("x");
      }
    }
  }

class Main {
  public static void main(String[] args) {
    Graph g = new Graph(5);
    g.addEdge(0, 1);
    g.addEdge(1, 2);
    g.addEdge(0, 3);
    g.addEdge(1, 3);
    g.addEdge(1, 2);
    g.addEdge(2, 4);
    g.addEdge(3, 4);
    g.showGraph();
  }
}
```
#### The output
![img](/compute/images/graph_list_output.PNG "Weird shit, right?")


#### The explanation
Let's tackle the obvious concepts above, the ones we see firsthand. We can see there's two classes, a `Graph` class and another mandatory `Main` class. We see that in the main class, we create an instance/object of the Graph class, called it `g` and added edges to it. Finally we called `showGraph()` function from `g` to print the graph.

The Graph class represents the graph (thanks man, so helpful). There's two member variables - an integer called `vertices`and another is an array of linkedlist called `adjList` that can hold integer values. Imagine this array of LinkedList as a _railway track_. This is the contiguos array. Now, for each gap in the track, we want to hold a collection/list of integer values. So imagine for each gap in the railway track, there extends a railway track. I know it doesn't make sense so here's a generic picture of what I mean:

![img](/compute/images/llist.png "A better explanation")

Next, in the graph class, we see a constructor which initializes the member variables. The vertices represent how many vertices are there in the graph while the adjList variable represents the graph in memory as an array of lists. The for-loop initializes the memory for each array index.

Finally,we see two functions -- `addEdge()` and `showGraph()`. The showgraph() function just prints out the graph in a fashion as you saw above. The addEdge() function takes in two parameters, a starting edge __u__ and an ending edge __v__, and adds them to the list. u - v represents the set of edges in a graph. So, A -> B translates to the edge 0 -> 1. Of course we could also use A -> B but I am too lazy to reformat the types above to Strings so meh.

#### But?
I know this was a terrible explanation of such a fancy data structure. Maybe I'll get better with re-iteration. Till then, thanks for reading till here. Next up, probably an intro to `Kotlin`? ( which I've been learning & man I am kinda excited).

_Thanks!_