---
title: Drivetrain Overview
---

The drivetrain forms the basis of locomotion for ground-based robotic systems. The primary elements are:
* the _chassis_, or supporting structure to which other elements mount,
* _traction devices_, such as wheels or tread, and
* _actuation source_, such as a DC brushed motor, to apply a force between the traction device and ground surface.

There are many variations of these elements, each which their own benefits and drawbacks depending on the end goal. 
Some decisions that factor into the drivetrain design are:
* _Degrees of freedom_ (DoFs), such as translation and rotation axes, which define how constrained the robot is when
it is moving about the field,
* _Stability_, or the ability to stay upright and in contact with the floor,
* _Wheel diameter_, which can increase ground clearance and reduce vibration at the cost of lower applied torque,
* _Wheel tread_, which impacts coefficient of friction and therefore traction (how "pushy" the robot is),
* _Motor type and quantity_, which impacts peak applied power and current draw (drivetrains historically are the most
power-hungry subsystem of an FRC robot)
* _Shape_, where a large convex polygon provides stability, but cutouts in that polygon may simplify integration
of certain mechanisms.


# Drivetrain Features

## Degrees of Freedom
As with any mechanism, the number of DoFs is a critical design aspect of the drivetrain. A car generally has 2 DOFs: forward/backward motion,
and steering. With these 2 DOFs, a car is able to move about on a 2-dimensional plane, but there are restrictions. For example,
a car cannot "strafe" sideways, which would make parallel parking much easier (and consequently many people would get drivers
licenses that don't deserve them!).

In our 3D world, rigid bodies can move in 6 degrees: 3 translational (forward/backward, left/right, and up/down) and 3 rotational (heading, pitch, and roll). 
FRC robots are actually constrained to 3 DOFs, much like a car, because they operate on a 2D plane. They cannot typically move vertically 
(such as a submarine or quadcopter), and they cannot pitch and roll (such as a fighter jet). 

In FRC, we usually see two types of designs:
* 2 DOF: one translational axis and one rotational axis. 
	* The skid-steer system (think of a tank) is the quintessential example. These cannot strafe left and right.
	* Other systems have been used in FRC, such as Ackermann steering, but these are rare.
	* A two-wheeled balancing robot is another example
* 3 DOF: two translational axes and one rotational axis.
	* These are known as omnidirectional or holonomic, since they can move in all unconstrained axes
	* Omni-wheel based systems have 3 or 4 omni wheels that are non-parallel. The force vectors form a basis in the
	2D plane, allowing motion in all 3 axes simultaneously
	* Mecanum wheels provide the same benefit as omni-wheels, but with the added benefit that the wheel axes can be
	parallel, which simplifies the design
	* Swerve systems combine the best of omnidirectional and skid-steer systems, at the expense of complexity: these
	systems provide full power to be applied to the wheels in any direction, but require sophisticated hardware and 
	control loops.

## Stability
We happen to live on Earth, which has gravity. As such, we (humans) must constaintly consider stability as we move about.
Our legs have evolved to be powerful and versatile, but we are essentially just walking inverted pendulums. We are naturally
unstable while standing.

Ground-based robots must also contend with gravity, even though they're inherently more stable. Trucks must turn at controlled
speeds to avoid tipping. Motorcycles can only accelerate so fast without popping a wheeling and sending their riders flying.

Stability comes in two flavors:
* _Static stability_: how stable is the system while sitting still?
* _Dynamic stability_: how stable is the system while moving about?

In both scenarios, the two key factors are the contact patch and the center of mass (CoM, or center of gravity, CG). The contact patch is the convex polygon
formed by all points of contact between the floor and the robot. The CoM is the average position in space of the rigid body (all
components rigidly mounted to the robot). The placement of the CoM over this contact patch determines whether the system is stable.
As the robot accelerates around the field, the acceleration vector and CoM form a force that acts on the robot. 

One way to imagine this is a "virtual" CoM: if the robot accelerates forward, the virtual CoM shifts backward. If it shifts 
so far backward that it is no longer over the contact patch, the robot may perform a wheelie! If a mechanism (arm or elevator)
shifts the CoM vertically, it becomes easier for an acceleration from driving to tip the robot.

Keep the CoM low so you can accelerate quickly! This means weight in the drivetrain isn't necessarily a bad trait.

## Actuation


## Wheels


## Chassis


# Further Reading
* [FRC125 Nutrons University Day: Drivetrains](https://www.youtube.com/watch?v=HpIlUxX6YI0&ab_channel=NUTRONS)
