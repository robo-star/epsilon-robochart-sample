Sample RoboTool project for Epsilon transformations
---------------------------------------------------

Install
=======

Currently this configuration targets the latest version of RoboTool.

1. Installing Epsilon
   
   Using the update site: http://download.eclipse.org/epsilon/updates/
   
   Installing the following features:
   
	* Epsilon Core
	* Epsilon Core Development Tools
	* Epsilon EMF Integration

Run
===

Run > External Tools > Epsilon Transforms.

Configuration
=============

*Source file*

By default only the 'test.rct' file is considered for transformation. This is
parametrised in the External Tools Configuration for "Epsilon Transforms" via
the parameter "SourceFile":

	-DSourceFile="test.rct"
	
There will be better ways in the future of specifying this for all relevant
files in the project, namely, including all necessary packages.

*Target file*

The source file ``test.rct`` is copied to ``test.target.rct``, and afterwards
the EPL transformation renames the RoboChart RCPackage, so that it can be
loaded alongside within RoboTool.

*Epsilon specifications*

These are under the ``erules`` folder.

*Orchestration of transformations*

This is performed by the ``build.xml`` ANT script. Currently only one EPL 
transformation ``erules/transform.epl`` is applied as many times as possible.

*Meta-model of RoboChart*

It is possible to select a different ECore model by changing the parameter
``metamodeluri`` in the 'build.xml' ANT script.
