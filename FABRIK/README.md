# FABRIK Implementation: 3D with joint motion constraints

Inverse kinematics in robotics is used to determine a set of joint angles acted on a chain of links needed for an end-effector to reach a desired position. A recent improvement in traditional inverse kinematics approaches is the Forward And Backward Reaching Inverse Kinematics (FABRIK) method.

The main issue was that there wasn't a publicly accessible FABRIK implementation / pseudocode that factored in motion constraints for a given joint, particularly limiting the range of motion for a joint while still reaching the desired position.

## FABRIK

FABRIK algorithm
---
Input:
  joint positions p_i, for i=1,2,...n
  target position t
  distances d_i=|p_i+1 - p_i|, for i=1,2,...n-1

Output:
  new joint positions p_i, for i=1,2,...n



FABRIK algorithm with constraints
---



# Sources
http://www.andreasaristidou.com/publications/papers/FABRIK.pdf
