---
layout: post
title: Graphs,graphs everywhere
date: 2020-07-08 22:57:00 +0530
permalink: /:title
---
Let me begin by addressing the thing that's bugging me..
I know it's been a `while` since I've posted. My last article ( [Javascript.js](https://damercy.github.io/compute/Javascript) ) would make you think that I started on a _js spree_ and never came back.

Well, I came back. But where was I the whole time, you ask?

I was _`learning`_. I was learning JS, diving into  all of the nitty-gritty features ---- IIFE's, Promises, Virtual DOM in React, maps-filters-reducers etc. I have been trying to get comfortable with AWS so that I may be able to deploy the sites (products?) efficiently.

> What is efficient deployment?

To me, it is when different components of a system (for example, a website) communicate with each other (the different modules) with ease, handling all the edge cases of null/undefined/form-manipulation. And do that with security in mind. The last thing I want in my production site branch is to have open ports in the EC2 instance. Hi, hacker.

Now that it is out of the way, let's talk about graphs. I really like graphs because
1. They sound fancy
2. They're fancy
3. FANCY

You see, graphs are an integral part of coding tests and I've been scared of this data structure since the 2nd year of my college when I struggled with it's mere implementation.

![img](/compute/images/graph.png "Tiger, Elephant & Graph")

> So how to implement a graph data structure?

It's easy contrary to what the past me used to believe. There's two major ways to denote a graph in computer:-
1. Adjacency matrix
2. Adjacency list.

### Adjacency matrix

![img](/compute/images/adm.png "What... matrix?")

Let's break down this seemingly "programmatic" name. `Adjancency` __->__ `Adjacent` __->__`Side by side`, right? `Matrix` __->__ Goddammit you know what a matrix is.

The idea is that the column and row labels would indicate the nodes and the connection between any two nodes (edges) will be represented by the value in the matrix. Let's see an example. Consider the following graph:-

![img](/compute/images/adm-g.png "What... matrix?")

The nodes are A,B,C,D,E which are connected by edges. Right beside it is it's adjacency matrix representation.
```Java
class AdjacencyMatrix{
    public static void main(String[] args){
        int adjacencyMatrix = new int[5][5]; // 5x5 matrix for 5 nodes
        for(int i=0;i<5;i++)
            for(int j=0;j<5;i++)
                adjacencyMatrix[i][j]=0; //Initially, there's no connection b/w nodes, hence 0

        /*
        Now here comes the map. In the above graph, the nodes are labeled as characters viz. A,B,C,D,E. But we need to somehow represent it in the matrix. So we map the characters to matrix indices. Thus, A->0,B->1,C->2,D-3,E->4. This mapping is done for all the graphs. Now, adjacencyMatrix[A][B] -> adjacencyMatrix[0][1].

        Another thing is that this is an undirected graph, so everytime we input for A->B, we need to input for B->A as well.

        What's an undirected graph? A graph that has no sense of direction aka no arrows pointing towards a direction. That's it!
        */

        adjacencyMatrix[0][1]=1; // A->B
        adjacencyMatrix[1][0]=1; // B->A
        adjacencyMatrix[0][3]=1;
        adjacencyMatrix[3][0]=1;
        adjacencyMatrix[3][1]=1;
        adjacencyMatrix[1][3]=1;
        adjacencyMatrix[1][2]=1;
        adjacencyMatrix[2][1]=1;
        adjacencyMatrix[2][1]=1;
        adjacencyMatrix[3][4]=1;
        adjacencyMatrix[4][3]=1;
        adjacencyMatrix[2][4]=1;
        adjacencyMatrix[4][2]=1;

    }
}
```
That's how easy it is to represent a graph! The second way, using adjacency list, may seem a tad bit complex but I assure you, it's easy. Well, this post has gotten too long for your short attention span.

The next post will be about how to represent a graph using adjacency list. Stay tuned!

