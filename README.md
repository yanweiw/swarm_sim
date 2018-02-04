# Swarm Robotics

This repo demonstrates the implementation results of three multi-agent algorithms, pertaining to the coordination, segregation, and locomotion of a robot swarm respectively. I implement the algorithms on kilobots and simulate their behaviors. [Kilobot](https://www.kilobotics.com/) is a low cost swarm robot designed by my professor Michael Rubenstein, and more details can be found [here](https://dash.harvard.edu/bitstream/handle/1/9367001/rubenstein_kilobotlow.pdf?sequence=1).

![kilobot](image/kilobot.png)

## Coordinate system based on Hopcount

In a multi-agent distributed system, it is always useful for robots to communicate its relative position in order to deliver coordinated behavior. Hopcount, a metric that represents how many hops one robot needs to get to another robot, is used to approximate distance between agents to triangulate the relative position of a robot within a swarm. In the simulation below, a swarm of static kilobots will first communicate with each other, shown by color changes, and then form the letter "N" of "Northwestern" as a group. More details of the algorithm are in this [paper](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.7.8705&rep=rep1&type=pdf).

![disp_N](image/disp_N.gif)

### Segregation based on Brazil nut effect

Often times it is helpful for a robot swarm to segregate into different functional groups. One distributed way of achieving segregation is through the Brazil nut effect: Through shaking the largest particles usually end up on the surface of a granular material containing a mixture of variously sized objects. A typical example is a container of mixed nuts, and Brazil nuts are usually the largest. In the simulation, kilobots of different color have different virtual radii and thus will segregate into three groups through their interaction. More details regarding the algorithm can be found [here](http://naturalrobotics.group.shef.ac.uk/supp/2012-001/)

![brazil](image/brazil.gif)

### Locomotion based on Reynolds flocking

[Starling flock](https://www.youtube.com/watch?v=eakKfY5aHmY) is one of the most spectacular swarm behaviors found in nature. When one starling changes direction or speed, its neighbors will respond to the change almost simultaneously and the change will propagate throughout the flock lightning fast regardless of its size. As no single starling dictates the movement of the flock, interesting patterns can emerge from the collective behavior. This simulation tries to replicate this swarm behavior by implementing Reynolds flocking, which is characterized by three rules: keep separation to avoid crowding, maintain alignment with the average heading of local flockmates, and retain cohesion to move towards the center of local flockmates. The algorithm is detailed in this [paper](https://infoscience.epfl.ch/record/169280/files/IROS11_Hauert.pdf).

![flocking](image/flocking.gif)

### Code

I decide not to put up my code in a public repo as these simulations are likely to be assigned as homework for the future swarm robotics class. If you have any questions about my implementations, you can find contact info at my [portfolio page]().
