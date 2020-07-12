# ROS_Publisher_Subscriber_Nodes
This is the 'HELLO WORLD' experiment with ROS .

System and platforms info.
Ubuntu 18.4, ROS melodic, tensorflow, Jupyter lab, Python 3.7



- First, creat ROS work space (ws)
- Seconed, creat new pakage (tests)
- Then, and in order to make the nodes able to communicate to each others, download those two libraries

rospy 
 https://github.com/ros/ros_comm.git
 
std_msgs
 https://github.com/ros/std_msgs.git 
downloade and extracted into the src file in your work space.

- After that, once you've created a package.xml, you should set the license (<license> tags) 
 and the maintainer name (<maintainer> tags) and adding your deppendecies. 
 
  <buildtool_depend>catkin</buildtool_depend>
  
   
  <run_depend>python-tensorflow-pip</run_depend>
  
  
  <build_depend>rospy</build_depend>
  
  <build_depend>std_msgs</build_depend>
  
  
  <exec_depend>rospy</exec_depend>
  
  <exec_depend>std_msgs</exec_depend>
  
  
- For CMakeLists.txt file, edit the catkin_install_python() call : 
   catkin_install_python(PROGRAMS scripts/talker.py DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})
   


 
- Now, go to your work space directory in terminal and type this command to include all the libraries you have imported
   $ catkin_make



I used Jupyter lab and tenseflow to excecute and run the publisher and subscriper nodes files.
You can use any python editor and then run it using the terminal after source the bash file using the command

$ source devel/setup.bash 
into your work space directory

then into your pakage directory type the commands  
$ chmod +x p.py

$ chmod +x s.py

and then send the massage to the topic with publisher
$ rosrun tests p.py

after that, open a new tirminal and do the same starting from sourcing the bash folder
except the command used to run the subscriber file is
$ rosrun tests s.py
