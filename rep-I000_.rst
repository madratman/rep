::
    
    REP: I000_
    Title: Hybrid free-space and semi-constrained path planning
    Author: Ratnesh Madaan
    Status: Draft
    Type: ??
    Created: 19-May-2015

Outline
=======

#. Abstract_
#. Motivation_
#. Definitions_
#. Requirements_
#. `Design Assumptions`_
#. Specification_
#. Rationale_
#. `Todo's`_
#. `Reference Implementation`_
#. References_
#. Copyright_


Abstract
========

This REP proposes (a draft procedure) to combine Descartes(semi-constrained) and MoveIt!(free-space) path planning libraries in a ROS package. It is relevant for users who require a motion plan for a combination of both kinds of trajectory segments. This will be adapted in the future if the proposed Descartes ROS msg API is modified. The project is code-named Hamilton and the repository is available [here](https://github.com/ros-industrial-consortium/hamilton).

Motivation
==========
The motivation for Descartes can be found in rep-I0003. MoveIt! is the widespread used library for free space planning- especially pick and place. The idea is to give the user a hybrid planning library that allows an integration of both the capabilities and can be applied to broader and more varied use cases in the industrial robotics arena. 

Definitions
=========

Requirements
=========
 * The library should take in a combination of several free space and semi-constrained paths and output a MoveIt! trajectory for execution. 

 * Make the planner user-friendly : inputs should be easy to specify, and change for that matter.  

 * The library should be general and flexible to accomodate possible use cases. This includes the requirement for generating free-space or semi-constrained paths for inputs given as :

    - Poses(EigenSTL::vector_Affine3d object)

    - Semi-constrained Points(descartes_trajectory::CartTrajectoryPt or AxialSymmetricPt or JointTrajectoryPt)

    - Add current pose(in RViz) as a free space or semi-constrained(ask user for the tolerances or axial symmetric axes and relevant descretizations)

    - Method to append descartes_core::TrajectoryPtPtr for tool pose using seed pose (a member variable) and translation and orientation offsets(inputs from user).  

    - There are a lot of possible constructors for creating descartes_trajectory points and moveit. Use inherited classes.

    - Allow user to set names for target poses.

    - Thinking along the lines of MoveIt! now, it is better to ask from the users two fields in each possible case. Tolerances are zero by default, and hence it is a free-space point. 

    - Functionality for simple curves - line, circle, etc for both types. 

    - Ask input for velocity at each point/tracjectory segment from each user. 

    - Ask to specify interpolation type. 

    - All this to be done in a GUI. Goal/CP position, orientation, velocity, constraints/tolerances. 

    - Velocity generator methods.   

  * MoveIt! has a lot of other functionalities as well. No one will use Hamilton if we provide only the above functions. 

  * Incorporate Fermi. 

  * Method to create a descartes robot model (as done in the ROS-I training classes for UR5.) Better (or other) options: 
    - Build over MoveIt! setup assistant. 
    - Descartes/Hamilton setup assistant. 
    - Maybe this is overkill, and this can be achieved by ROS plugin lib.(as done in Godel.) 

Design Assumptions
========= 

Specification
=========

Rationale
==========

Todo's
=========
 
Reference Implementation
==========
 
References
==========

Copyright
=========

This document has been placed in the public domain.

 
..
   Local Variables:
   mode: indented-text
   indent-tabs-mode: nil
   sentence-end-double-space: t
   fill-column: 70
   coding: utf-8
   End:
