# FABRIK Implementation: 3D with joint motion constraints

Inverse kinematics in robotics is used to determine a set of joint angles acted on a chain of links needed for an end-effector to reach a desired position. A recent improvement in traditional inverse kinematics approaches is the Forward And Backward Reaching Inverse Kinematics (FABRIK) method.

The main issue was that there wasn't a publicly accessible FABRIK implementation / pseudocode that factored in motion constraints for a given joint, particularly limiting the range of motion for a joint while still reaching the desired position.

## FABRIK

The algorithm consists of two stages: a forward-reaching stage, and a backward-reaching stage - hence the acronym. The forward-reaching stage estimates the new joint positions are found by iterating from end-effector to base positions, where new directions are computed based on consecutive joint positions, given that the end-effector's position is set to the desired position. As for the backward-reaching stage, it works similarly but fromm base to end-effector and starting off with resetting the base joint position, considering that the forward-reaching stage re-assigns the base joint.

Essentially, think of forward-reaching as if one were to detach the base joint and reach the desired position - the best case scenario. Realistically, the base joint position is fixed, so the backward-reaching stage is needed. After repeating this for a great number of iterations, it should ideally consist of a final set of joint positions where the end-effector joint reaches the desired position within a reduced distance after each iteration of both stages.

While this ended up being a great improvement in the inverse kinematics approaches previously done, there wasn't any real guidance I could find that could factor in motion constraints about each joint. For instance, the average human knee joint has a range of 0 to 135 degrees, and only done around one axis. Speaking of said axis, what if the axis isn't with respect to the axis of the human body? Maybe that axis itself requires a new orientation.

My attempt reworks the existing FABRIK implementation to factor in such constraints.


# Sources
http://www.andreasaristidou.com/publications/papers/FABRIK.pdf
