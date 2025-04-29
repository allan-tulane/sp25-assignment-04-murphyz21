# CMPS 2200 Assignment 5
## Answers

**Name:**__Zoe Murphy___



- **1a.**
logd(n) depth

- **1b.**
Delete Min: O(d logd(n)) work because you have to like compare d children for each level
Insert: O(logd(n)) work because it corresponds with the depth and adding nodes at the end

- **1c.**
The new bound on the work would be O(|V| * dlogd(|V|) + |E| * logd(|V|)). It's just like plugging in the work values we have for delete min and insert. 

- **1d.**
You could set d as |E|/|V|

- **2a.**
APSP(0,0,0) = 0
APSP(0,1,0) = 2
APSP(0,2,0) = inf
APSP(1,0,0) = inf
APSP(1,1,0) = 0
APSP(1,2,0) = 1
APSP(2,0,0) = -2
APSP(2,1,0) = 0
APSP(2,2,0) = 0

APSP(0,0,1) = 0
APSP(0,1,1) = 2
APSP(0,2,1) = inf
APSP(1,0,1) = inf
APSP(1,1,1) = 0 
APSP(1,2,1) = 1
APSP(2,0,1) = -2
APSP(2,1,1) = 0
APSP(2,2,1) = 0

APSP(0,0,2) = 0
APSP(0,1,2) = 2
APSP(0,2,2) = inf
APSP(1,0,2) = inf
APSP(1,1,2) = 0
APSP(1,2,2) = 1
APSP(2,0,2) = -2 
APSP(2,1,2) = 0
APSP(2,2,2) = 0


- **2b.**
Yes I see a pattern between all of them and the patterns are easy to see because of how I grouped the answers above. You can write it like
APSP(i,j,2) = min(APSP(i,j,1), APSP(i,2,1) + APSP(2,j,1)).

- **2c.**
APSP(i,j,k)= min(APSP(i, j, k-1), APSP(i, k, k-1), APSP(k, j, k-1)

- **2d.**
We would have three sub-problems for this (think one for i, one for j, and one for k) and they each have a work of n and would become O(n^3) total work.

- **2e.**
Johnson's algorithm has a work of O(|V|*|E| + |V^2|log|V|). V^3 (from 2d) is really bad if V is a big number. Overall I would go with Johnson's cause it's overall a bit more efficient. 


- **3a.**
No, the MST tree is not going to be a guaranteed solution to MMET. It can sometimes be a solution, but not always. THe MMET tree will just look at the maximum weight of any edge, but the MST looks at all the edges, leading to it potentially having a higher total weight. 

- **3b.**
First you would want to find the edge with the highest weight in the MST. Then, get rid of that edge. That will split some things up in the MST, so then you'll want to reconnect the graph back together with the smallest edge and add it back to the tree and return the tree. You might have to do this a few times if there are a few edges with the highest weight. 

- **3c.**
Finding the edge with the heighest weight will take O(E) time, removing the edge is O(1), and then repeating this is another O(E) time, so the total work can be O(E^2). 
