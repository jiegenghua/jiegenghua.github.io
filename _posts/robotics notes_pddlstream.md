---
title: 'Robotic Notes: pddlstream learning'
date: 2024-12-01
permalink: /posts/2024/12/blog-post-21/
tags:
  - pddlstream
  - maniskill
  - task planning
---

# What is pddlstream and why do we need it?



# Explanation
## domain.pddl
Given a domain.pddl file, 

the following is a detailed explanation of this file:

?b: the name of a block
?r: the name of a region on a stable surface
?p: 6 DOF block pose placed stably on a fixed surface
?g: a 6 DOF block transform relative to the robot gripper
?q: an 11 DOF robot configuration
?t: a trajectory composed of a finite sequence of waypoing robot configurations

### Fluent predicates: 
AtConf: model the changing robot configuration
AtPose: object pose
Holding: gripper status
Empty: gripper status

### static predicates
- Block: declare that ?b is a block
- Conf: declare that ?q is a robot configuration
- Pose: a pose ?p can be used for block ?b
- Grasp: a grasp ?g can be used for block ?b
- Kin: a kinematic constraint
- Motion: a constraint that ?q1, ?q2 are the start and end configurations for trajectory ?t, and ?t satisfies the joint limits, self-collisions, and collisions with the fixed environment
- Contain: when block ?b is at pose ?p, it is within region ?r
- CFree: if block ?b was placed at pose ?p, the robot, executing trajectory ?t, would not collide with it
- Dist: cost function, gives the distance traveled along trajectory ?t


### action
- move
- pick
- place

## derived predicates
- In: express whether block ?b is currently contrained within region ?r by expressing a condition on its current pose ?p
- Safe: encodes whether trajectory ?t does not collide with placed block ?b at its current pose

# stream.pddl
## stream
- poses: randomly samples an infinite sequences of stable placements ?p for clock ?b in region ?r.
- grasps: enumerates a sequence of force-closure grasps ?g for block ?b
- ik: calls an inverse kinematics solver to sample configurations ?q from a 4d MANIFOLD of values (due to manipulator redundancy) that enable the robot to manipulate a block ?b at pose ?p with grasp ?g.
- motion: repeatedly calls a motion planner to generate safe trajectories ?t between paris of configureations ?q1. ?q2
- cfree: test whether block ?b when at pose ?p is collision free with respect to all robot configurations along trajectory ?t. It is a test stream with no outpt parameters. If it generates the empty tuple <>, its certified conditions are proven. cfree is checked by calling a collision checker along trajectory ?t.
- Dist: external cost function, which returns the sum of the distance between each pari of adjacent configuration waypoings on trajectory ?t


# pddlstream algorithm
- Incremental
- Focused
- Binding
- Adaptive



# example using maniskill+sapien



# Reference






















