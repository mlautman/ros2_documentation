Building RQT2 from Source
=========================

System Requirements
-------------------

These instructions are written for the target platforms for Crystal
Clemmeys (see `REP <http://www.ros.org/reps/rep-2000.html>`_).

- Ubuntu Bionic Beaver 18.04 64-bit
- Windows 10 with Visual Studio 2017
- Mac OSX Sierra 10.12.x

*Note:* Windows 10 has limited support at the moment. The Python plugins should work but C++ is a work in progress.

Other Requirements
~~~~~~~~~~~~~~~~~~

- In ROS2 Crystal the minimum Qt version is ``Qt5``
-

Building From Source
--------------------

In order to build RQT2 from source, first create a ROS2 workspace at ``~/ros2_ws/``.
This is step is already covered in building ROS2 from source instructions, so we skip it here.

As of this writing (Dec 2018) you must install ROS2 from source alongside RQT2. See `Building ROS2 from source <https://index.ros.org/doc/ros2/Installation/>`_.

*Note:* RQT2 has only been tested with the master branch of the ``ros2.repos`` file. It is important that while setting up your ROS2 workspace, you replace:

      https://raw.githubusercontent.com/ros2/ros2/release-latest/ros2.repos

with:

      https://raw.githubusercontent.com/ros2/ros2/master/ros2.repos


Download RQT2 Repositories
~~~~~~~~~~~~~~~~~~~~~~~~~~

::

   cd ~/ros2_ws
   wget https://raw.githubusercontent.com/PickNikRobotics/rqt2_setup/master/rqt2.repos
   vcs import src --force < rqt2.repos

 **TODO:** The wget command should be replaced with an invocation of ``rosinstall_generator`` as soon as the packages have been released.


Install Dependencies
~~~~~~~~~~~~~~~~~~~~

::

   rosdep install --from-paths src --ignore-src --rosdistro bouncy -y --skip-keys "console_bridge fastcdr fastrtps libopensplice67 rti-connext-dds-5.3.1 urdfdom_headers rqt_gui_cpp"

**Note:** As of Dec 2018 some dependencies are skipped including *rqt_gui_cpp* which
aren’t yet fully ported or are othewise not yet available from rosdep.

Build The Workspace
~~~~~~~~~~~~~~~~~~~

::

   colcon build

Advanced Colcon usages:

-  Show verbose output:

   ::

     colcon build –event-handlers console_direct+

-  Only build one package and its dependencies:

   ::

     colcon build –packages-up-to rqt_shell

Source your environment
~~~~~~~~~~~~~~~~~~~~~~~

::

   . install/local_setup.bash


Using RQT2
----------

See `Overview of RQT2<RQT2-Overview-Usage>`.
