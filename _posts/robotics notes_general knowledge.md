---
title: 'Dynamics, inverse dynamics, kinematics, inverse kinematics'
date: 2024-09-02
permalink: /posts/2024/09/blog-post-2/
tags:
  - robotics
  - optimization
---


# forward dynamics
predicts the motion of a system given forces and torques



# inverse dynamics





# Inverse kinematics


# motion planning 
## screw
### how it works
fast, smooth, almost straight end-effector motion in task space.
can not handle obstacles

### when to use it
- approach
- pick/place
- minimal collision risk and good manipulability
## RRT
a sampling based planner
can handle obstacles

### when to use it
- cluttered scenes/ narrow passages/ obstacles
- when screw fials or ik along the way is not feasible
# examples
## Dexterous hand