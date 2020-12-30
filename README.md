# Swarm Robotics

This repo demonstrates the implementation results of three multi-agent algorithms, pertaining to the coordination, segregation, and locomotion of a robot swarm respectively. I implement the algorithms on kilobots and simulate their behaviors. [Kilobot](https://www.kilobotics.com/) is a low cost swarm robot designed by professor Michael Rubenstein. More details can be found [here](https://dash.harvard.edu/bitstream/handle/1/9367001/rubenstein_kilobotlow.pdf?sequence=1).

![kilobot](image/kilobot.png)

### Coordinate system based on Hopcount

In a multi-agent distributed system, it is necessary for robots to communicate their relative position before delivering coordinated behaviors. Hopcount, an approximate representation of how far one robot is from another, is used to triangulate the relative position of a robot within a swarm. In the simulation below, a swarm of static kilobots will first communicate with each other, marked by color changes, before forming the letter "N" of "Northwestern" collectively. More details of the algorithm are presented in this [paper](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.7.8705&rep=rep1&type=pdf).

#### Notes for Sharon
<mark>
Think of each circle in the gif below as a small robot. They are all identical and stationary. Each robot does not know its global location in terms of say a (x, y) coordinate in the swarm, but it knows its relative coordinate with respect to its neighbors, e.g. it is one hop to the right of its left neighbor, and two hops above the neighbor that is two hops below it. The goal is for each robot to figure out its global coordinate through only talking to its neighbors, i.e. every robot can only talk to robots that are within say two hops away in each direction. If every robot can figure out its global coordinate, then we can ask the swarm to display a global pattern in coordination. The trick to achieve this goal is to let robots at the corner start propagating messages inward in a wave like pattern as shown by red/blue/green stripes. Once the coordination is done, we show proof that every robot knows its global coordinate by displaying a N-shaped letter.
</mark>

![disp_N](image/disp_N.gif)

### Segregation based on Brazil nut effect

Often times it is helpful for a robot swarm to segregate into different functional groups. One distributed way of achieving segregation is through the Brazil nut effect: The largest particles in a bag of variously sized objects usually end up on the surface after shaking the bag. A typical example is a container of mixed nuts, and Brazil nuts which are the largest usually appear on top. In the simulation kilobots of different color have different virtual radii and thus will segregate into different groups through their interaction. More details regarding the algorithm can be found [here](http://naturalrobotics.group.shef.ac.uk/supp/2012-001/)

#### Notes for Sharon
<mark>
Again each colored dot represent a robot, and robots with the same color are from the same group. We want to separate these initially mixed robots into three distinct groups by color. Each robot can only talk to its immediate neighbors due to limited communication range to figure out if they are from the same group or not. We want to achieve global segregation via only local messaging. The key intuition is that if you shake a bag of mixed nuts you usually end up with a bag with big nuts at the top and small nuts at the bottom (small nuts can fall under through the cracks between big nuts due to shaking). We borrow this idea by giving each blue robots the largest virtual radius (the distance a robot has to maintain with its neighbors) and red robots the smallest virtual radius. We then let all the robots mingle with each other and through repulsion force due to the need of maintaining virtual radius, the red robots will end up in the center closest to one another while the blue robots will end up in the exterior farthest from one another.
</mark>

![brazil](image/brazil.gif)

### Locomotion based on Reynolds flocking

[Starling flock](https://www.youtube.com/watch?v=V4f_1_r80RY) is one of the most spectacular swarm behaviors found in nature. When one starling changes direction or speed, its neighbors will respond to the change almost simultaneously and thus the change propagates throughout the flock lightning fast regardless of its size. As no single starling dictates the movement of the flock, interesting patterns can emerge from the collective behavior. This simulation tries to replicate this swarm behavior by implementing Reynolds flocking, which is characterized by three rules: keep separation to avoid crowding, maintain alignment with the average heading of local flockmates, and retain cohesion to move towards the center of local flockmates. The algorithm is detailed in this [paper](https://infoscience.epfl.ch/record/169280/files/IROS11_Hauert.pdf).

#### Notes for Sharon
<mark>
This one simulates birds flocking. Each red dot is a bird. No one is a leader and every one just follows what its neighbors are doing locally. But globally we get this perfect coordinated flocking pattern as if the group has a leader.
</mark>

![flocking](image/flocking.gif)

### Code

I decide not to put up my code here as these simulations are likely to be assigned as homework for the future swarm robotics class. If you have any questions about my implementations, you can find me at my [portfolio page](https://yanweiw.github.io/). Cover photo credit to [Harvard SEAS](https://www.seas.harvard.edu/news/2014/08/self-organizing-thousand-robot-swarm).
