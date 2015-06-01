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

This REP proposes (a draft procedure) to combine Descartes(semi-constrained) and MoveIt!(free-space) path planning libraries in a ROS package. It is relevant for users who require a motion plan for a combination of both kinds of trajectory segments. This will be adapted in the future if the proposed Descartes ROS msg API is modified. 

Motivation
==========
The motivation for Descartes can be found in rep-I0003. MoveIt! is the widespread used library for free space planning- especially pick and place. The idea is to give the user a hybrid planning library that allows an integration of both the capabilities and can be applied to broader and more varied use cases in the industrial robotics arena. 

Definitions
=========

Requirements
=========
 * The library should take in a combination of several free space and semi-constrained paths and output a joint trajectory for execution. 
 * Most robots supported by ROS-Industrial offer a FollowJointTrajectory action interface for both simulation and actual hardware. This is to be taken care of. 

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
