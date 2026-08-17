``` mermaid
---
title: First Flowchart
---
flowchart LR
  id0-->id1
  id1-->id2
  id2-- Here is the text on the link -->id3
  id3-- Here is another text on the link -->id4
  id0["This is a node with a Unicode character ♥"]
  id1[This is another rectengular shaped node.]
  id3[Here is just a node for another introduction]
  id4[as well as this node just for an introduction]
```
Possible FlowChart orientations are:
* TB - Top to bottom
* TD - Top-down/ same as top to bottom
* BT - Bottom to top
* RL - Right to left
* LR - Left to right

Node shapes 

**A node with round edges**

Code:
  id3()