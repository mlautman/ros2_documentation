Overview and Usage of RQT2
==========================

RQT is a graphical user interface framework of ``ROS2`` that implements various tools and interfaces in the form of plugins.
One can run all the existing GUI tools as dockable windows within RQT! The tools can still run in a traditional standalone method, but RQT makes it easier to manage all the various windows in a single screen layout.

You can run any ``RQT`` tools/plugins easily by:

::

   ros2 run rqt_gui rqt_gui

This GUI allows you to choose any available plugins on your system.
You can also run plugins in standalone windows.
For example, RQT Python Console:

::

   ros2 run rqt_py_console rqt_py_console

 Users can create their own plugins for RQT with either ``Python`` or ``C++``.
 `Over 20 plugins<http://wiki.ros.org/rqt/Plugins>`_ were created in ROS1 and these plugins are currently being ported to ROS2 (as of Dec 2018, `more info <https://discourse.ros.org/t/rqt-in-ros2/6428>`_).

Installing From Debian
~~~~~~~~~~~~~~~~~~~~

TODO(Dec 2018): RQT2 is in active development for the ROS Crystal release.

::

   sudo apt install ros-$ROS_DISTRO-rqt*


Building From Source
~~~~~~~~~~~~~~~~~~~~

See `Building RQT2 from Source <RQT2-Source-Install>`

RQT Components Structure
------------------------

``RQT`` consists of three metapackages:

 * *rqt* - core infrastucture modules.
 * *rqt_common_plugins* - Backend tools for building tools.
 * *rqt_robot_plugins* - Tools for interacting with robots during runtime.

Advantage of RQT framework
~~~~~~~~~~~~~~~~~~~~~~~~~~

Compared to building your own GUIs from scratch:

 * Standardized common procedures for GUI (start-shutdown hook, restore previous states).
 * Multiple widgets can be docked in a single window.
 * Easily turn your existing Qt widgets into ``RQT`` plugins.
 * Expect support at `ROS Answers <http://answers.ros.org>`_ (ROS community website for the questions).

From system architecture's perspective:

 * Support multi-platform (basically wherever `QT <http://qt-project.org/>`_ and ROS run) and multi-language (``Python``, ``C++``).
 * Manageable lifecycle: RQT plugins using common API makes maintainance & reuse easier.

Further Reading
~~~~~~~~~~~~~~~

* ROS2 Discourse `announcment of porting to ROS2 <https://discourse.ros.org/t/rqt-in-ros2/6428>`_).
* `ROS1 documentation <http://wiki.ros.org/rqt>`_.
* Brief overview of ``RQT`` (from `an intern completion blog post <http://web.archive.org/web/20130518142837/http://www.willowgarage.com/blog/2012/10/21/ros-gui>`_).

  .. raw::

     <iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/CyP9wHu2PpY" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
