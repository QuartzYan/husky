^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package husky_control
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

0.6.3 (2022-05-16)
------------------
* Enable subst_value when loading config_extras. (`#226 <https://github.com/husky/husky/issues/226>`_)
* Remove whitespace
* Re-add base_frame_id and velocity_rolling_window_size
* Update DiffDriveController params
  - Remove `estimate_velocity_from_position: false` because it does not exist as a param in `DiffDriveController`, or anywhere in `ros-controllers`
  - Remove `base_frame_id: base_link` because the default value of `base_frame_id` is already `base_link`, as per http://wiki.ros.org/diff_drive_controller
  - Remove `velocity_rolling_window_size: 2` so `velocity_rolling_window_size` can take on the default value of 10. A higher value reduces the amount of noise in the odometry, as per: https://docs.google.com/document/d/1x1HOtLs9Z9jfuKdtSMM_YWOrWM4p08LJVt6vQVohVWI/edit#
* Contributors: Chris I-B, Joey Yang

0.6.2 (2022-02-15)
------------------
* Bump CMake version to avoid CMP0048 warning.
* Contributors: Tony Baltovski

0.6.1 (2022-01-18)
------------------
* Overwrite 'wheel_radius_multiplier' with env. var. HUSKY_WHEEL_MULTIPLIER
* Check launch file only if testing
  When building husky_control, husky_description, husky_navigation or
  husky_viz without tests, CMake fails as it does not find
  `catkin_run_tests_target` command. This patch adds conditions to fix
  this problem.
* predict odom->base_link tf to current time
* Contributors: Alexandre Iooss, Ebrahim Shahrivar, Luis Camero

0.6.0 (2021-09-28)
------------------

0.5.1 (2021-09-16)
------------------
* Remove the need to explicitly specify the laser_enabled, realsense_enabled, and urdf_extras arguments; use the envars to make it easier to simulate customized robots & use the moveit setup assistant.
* Contributors: Chris Iverach-Brereton

0.5.0 (2021-08-23)
------------------
* Disabled multimaster.
* Add the link_name parameter to fix the interactive markers in rviz
* Contributors: Chris Iverach-Brereton, Tony Baltovski

0.4.4 (2020-08-13)
------------------
* clearer wording
* change if to unless
* added env var and if-statement to disable robot ekf
* Remove support for the Kinect for Xbox 360. We've had the deprecation warning around for a while, so let's finally do it.  Realsense support is in-place as a drop-in replacement that gets added to the top rollbar, just like the old Kinect would have.
* Removed Paul Bovbel as maintainer.
* Finish adding the simulated realsense to the topbar, add support for the physical realsense. Tidy up some parameters that were copied in last night but not yet configured.
* Contributors: Chris I-B, Chris Iverach-Brereton, Jose Mastrangelo, Tony Baltovski

0.4.3 (2020-04-20)
------------------
* Update the udev rules to map the controllers to appropriate symlinks instead of relying on device enumeration to save us
* Remove the device override for the PS4 controller since we pair with bluez now (which maps the device to /dev/input/js0)
* Fix the filename in the launch fike
* Make the Logitech controller config file explicit. Add ascii-art controllers to label the axes to make configuration easier
* Contributors: Chris I-B, Chris Iverach-Brereton

0.4.2 (2019-12-11)
------------------

0.4.1 (2019-09-30)
------------------
* Added envar for joy device.
* Contributors: Tony Baltovski

0.4.0 (2019-08-01)
------------------

0.3.4 (2019-08-01)
------------------

0.3.3 (2019-04-18)
------------------

0.3.2 (2019-03-25)
------------------

0.3.1 (2018-08-02)
------------------
* Updated default controller to be PS4.  Can be set back to logitech (legacy) by setting HUSKY_LOGITECH environment variable
* Contributors: Dave Niewinski

0.3.0 (2018-04-11)
------------------
* Updated all package versions to 0.2.6.
* Made multimaster not come up by default in husky_control
* [husky_control] Fixed typo.
* Updated the rolling window size for more responsive control
* Fixed typo in URLs.
* Added dependency on husky_description to husky_control/package.xml
* Remove defunct email address
* Updated maintainers.
* Added more details to the config_extras workflow.
* Temp commit
* Add interface definitions
* Revert "Remove twist_mux config."
  (cherry picked from commit 4ae73877d0d3b0db8e6bc6be18f0648ea310d372)
* Update bringup for multirobot
* Purge more UR; Implement urdf_extras
* Update URDF for multirobot
* Remove twist_mux config.
* Replace twist-mux
* Contributors: Administrator, Dave Niewinski, Paul Bovbel, Peiyi Chen, TheDash, Tony Baltovski

0.2.7 (2015-12-31)
------------------
* Update localization.yaml
* Update localization.yaml
* Remapping the move_base topic to be compatible with cpr autonomy core.
* Contributors: Peiyi Chen, Tom Moore

0.2.6 (2015-07-08)
------------------
* Added angular_scale_turbo to teleop.config.
* Move interactive marker launch from teleop into control launch file
* Added fix for ur5 arm in gazebo
* Contributors: Paul Bovbel, Devon Ash, Tony Baltovski

0.2.5 (2015-04-16)
------------------

0.2.4 (2015-04-13)
------------------

0.2.3 (2015-04-08)
------------------


0.2.2 (2015-03-23)
------------------
* Fix package urls
* Contributors: Paul Bovbel

0.2.1 (2015-03-23)
------------------
* Update control params with base_link
* Contributors: Paul Bovbel

0.2.0 (2015-03-23)
------------------
* Add UR5 arm simulation control config
* Contributors: Paul Bovbel, Devon Ash

0.0.4 (2015-02-12)
------------------
* Namespace fixes
* Contributors: Paul Bovbel

0.0.3 (2015-02-06)
------------------

* Update website
* Add author
* Get rid of chassis_link, switch to base_footprint and base_link
* Turn on 2d mode; future proof robot_localization parameters
* Refactor configuration files into modules
* Re-enable IMU orientation fusion
* Contributors: Paul Bovbel

0.0.2 (2015-01-16)
------------------
* Use odom position for ekf
* Update wheel separation multiplier for slippage
* Restore teleop twist joy
* Set 2D mode, and add move_base cmd channel
* Contributors: Paul Bovbel

0.0.1 (2015-01-12)
------------------
* Initial development of husky_control for Husky indigo release
* Contributors: Paul Bovbel
