Overview
========

`Open_street_map`_ is a repository of ROS_ packages for working with
`Open Street Map`_ information.

**Warning**::

  The master branch normally contains code being tested for the next
  ROS release.  It will not always work with all previous releases.
  Sometimes, it may not work at all.

The current master works with Hydro and Indigo.  To build for Fuerte
or Groovy, check out the rosbuild branch instead of master.

.. _`Open Street Map`: http://openstreetmap.org
.. _`Open_street_map`: http://www.ros.org/wiki/open_street_map
.. _ROS: http://www.ros.org

Update in this Fork
========

Its a fork of https://github.com/ros-geographic-info/open_street_map.git (branch:master).
Modified the scripts to make it work with Ubuntu 20.04 with ROS1 and Python 3.8.10

Tips for your own .osm files:
========
* Copy your .osm file into the osm_cartography/tests folder. And check one of the lat, lon points from that file (these files can opened in any text editor)
* Open python3 in terminal, type import geodesy.utm
* geodesy.utm.fromLatLong(oneofpointsLat, samepointLon).toPoint() to get the x and y of that point.
* type that particular x and y into the static_transform_publisher. 
* For example if the output of previous step is x=662525 and y=5771365. Then use following in terminal, 
  ```rosrun tf static_transform_publisher 662525 5771365 0 0 0 0 1 map local_map 100```
