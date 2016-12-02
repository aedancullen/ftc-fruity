# fruity
Omnidirectional Driving and Path Planning for FIRST Tech Challenge

Fruity is an omni-directional driving controller for FIRST Technical Challenge robotics competitions. It allows for simple control of robots configured with multiple pairs of angled holonomic wheels which can be collectively driven to allow for maneuverable navigation in any direction. Fruity provides a simple API which allows the user to input a target angle at which to drive, a rate at which to drive in that direction, and additionally a rate of rotation which should be carried out at the same time as the translation. 

## Driving base configuration
Wheel configurations are laid out in an organized fashion, with several pre-configured for common driving base designs. Motor rotation direction (as would differ for motors on each side of the robot) is additionally computed on the fly and does not need to be pre-programmed by the user. This entire kinetic automation and maneuverability in a driving base is unique in the community of typical "differential - drive" robots.

## Forward-heading compensation
Support is also provided for inertial measurement units, which can be utilized in order to allow for heading compensation, or the adjustment of the input target driving angle such that the forward direction is always the direction facing away from the robot driver. This feature implicitly allows for the usage of asynchronous rotation at the same time as translation -- since on each iteration of the algorithm the forward direction will be updated. Thus, the robot  will continue translating in the same direction even as it rotates in place. 

## Path planning and following
Since it is often necessary to program a robot to follow a specific, predefined path autonomously, Fruity provides support for the reading of files from external storage in a comma-separated values format which defines segments of motion and their parameters which the robot will follow. Such files can be edited directly using a spreadsheet application on a PC, then transferred to the phone's external storage for use. These files specify in which direction the robot should drive, the distance of the driving, the speed that should be used, and other data.

## Use in Android Studio
This repository is provided as a module that can be imported into Android Studio in order for other programmers to integrate the Fruity driving controller into their own code. In order for the API to become accessible from the ftc_app TeamCode module, a compile dependency can be added to the TeamCode module which requires the Fruity module.
