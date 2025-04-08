---
{"dg-publish":true,"permalink":"/content/digital-garden-content/artificial-intelligence-content/alpha-beta-pruning/","created":"2025-04-08T20:04:02.909+05:30","updated":"2025-04-08T20:04:50.076+05:30"}
---

#DigitalGarden

## What is Alpha Beta Pruning

>[!important]
>It is a type of search time minimizing method that prunes forests or trees such that certain branches of nodes are not considered anymore by following a specific algorithm

The rules and constraints are as follows:
- There are two variables to be considered, alpha ($\alpha$) which represents the max value and then beta ($\beta$) which represents the minimum value
	- Alpha starts with -∞
	- Beta starts with +∞
- Each layer with have the tag max or min in it
	- If the layer specifies max, then the max variable will change and check the node below it to see if a value is greater than it
	- If the layer specifies min, the min variable will change and check the node below it to see if a value is less than it
- If a min layer below has a value smaller than the min value already at that layer, it will change that value. Vice versa for a max layer, if there is a value bigger than the layer below it, it will change into it
- If alpha $\geq$ beta ($\alpha \geq \beta$), then whatever node branch was not visited after making this statement will be pruned

Take the following figure for example to see how this logic is implemented:

![Pasted image 20250407081516.png](/img/user/pngs/Pasted%20image%2020250407081516.png)

To conclude, what makes an alpha-beta pruning algorithm efficient is the fact that it can prune off branches that it does not need based on the simple logic "$\alpha \geq \beta$", hence making it such that when a node has an alpha value greater than a beta or equal to it, the branches following will not be considered.