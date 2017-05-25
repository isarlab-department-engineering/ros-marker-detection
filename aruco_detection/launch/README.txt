if you want to customize aruco_detector node parameters create a launch file in this folder, where you set your proper values for the params that you want.

note: not every param that you might insert in your launch file is ready to be read in the aruco_detector node! you must check this out and, if needed, you must write a line
of code that let you to read the param from launch file. pay attenction on the default values you give. 
   
for examples refer to already existing launch file in this folder and to the aruco_detector node

TO-DO: make a default launch file where is loaded a default camera params and nothing else (all values going to be load from default ones)  