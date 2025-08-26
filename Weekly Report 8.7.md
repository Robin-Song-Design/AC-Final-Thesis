For the small prototype, I change the arrange type of the workdesks islands, dividing into A\B\C 3 types.![[Pasted image 20250806183320.png]]

## Observation:

1. C generally performs the best because it helped agents form lanes in the same direction as the evacuation.
2. Compare three types. The C performs the best in all cases except for cases where the path width is 2.0, 2.2 and 2.4. That means when the path width larger than 1.8m, it will not impact a lot on the agents moving, instead the original positions of agents influence more.
3. Compare path width 1.8, 2,0,2.2,2.4. We can see that there is a mutation between 2.0m and 2.2m. At 2.0m, the gate width before the exit is 2.23, and the crowd still shows merging behavior with alternating forward movement. At 2.2m, when the gate width is 2.43, two distinct streams of people can be clearly observed, which significantly accelerates the evacuation speed.
4. And also Type C when comparing 1,6m and 1.8m. The evacuation time actually increased with a 1.8m channel width. This is because at 1.8m, the width of the final exit becomes larger, allowing more agents to occupy the exit area at the same time. Due to the use of the social force model, there are interactive forces between agents (simulating the real-world situation where crowds push and shove against each other), which resulted in a decrease in evacuation speed.


5
Run one for the plan, see the trajectory. where most people walk.
check corridor doors & office doors
Both exit gates.
