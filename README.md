# Hand-Kinematics-Manipulation (in progress)
Mathematica simulation of a prosthetic hand using kinematics and grasp planning approaches to perform manipulation tasks on a given object.

This project emulates the motions and forces needed for a 3D CAD model of a prosthetic hand to grab and move an object.

Main source: https://www.cse.lehigh.edu/~trink/Courses/RoboticsII/reading/murray-li-sastry-94-complete.pdf

## Intended Flow

1. Configure position + orientation of each joint

2. Utilize Kinematics to reach a desired location

3. Calculate forces needed to grasp object

4. Derive hand jacobian matrix
