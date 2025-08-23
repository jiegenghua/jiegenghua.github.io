---
title: 'Robotic Notes: pddlstream learning'
date: 2024-12-01
permalink: /posts/2024/12/blog-post-21/
tags:
  - pddlstream
  - maniskill
  - task planning
---

## domain.pddl
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
- Motion: a constraint that 
- Contain
- CFree





















