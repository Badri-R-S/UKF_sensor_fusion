# Unscented Kalman Filter and Sensor Fusion for the 2-D position, velocity, yaw, and yaw rate tracking
In this project, an Unscented Kalman Filter and Sensor Fusion were utilized to estimate the state of a moving object of interest (bicycle) with noisy lidar and radar measurements. The system uses the CTRV motion model. This model is more robust when it comes to non-linear movements.
The available sensors were LIDAR and RADAR. LIDAR produces point cloud output from which the position of the bicycle can be found. RADAR uses the Doppler effect to give velocity output and the radial position.
The performance of the filter has been measured using the RMSE error metric. Along with the RMSE metric, to check the consistency of the filter and noise parameters, NIS measurements were also used.

## State
The state of the vehicle is defined by a 5-element vector as follows:
<p align="center">
<img width="600" height="400" src="https://github.com/Badri-R-S/UKF_sensor_fusion/blob/master/Results/state.png"
</p> 
  
- px is the x-position of the bicycle.
- py is the y-position of the bicycle.
- v is the magnitude of the velocity of the bicycle.
- psi is the yaw of the bicycle.
- psi_dot is the yaw rate of the bicycle.
Yaw rate provides rich information about the turning speed of the vehicle. It is important because it can be used to predict changes in the direction and orientation of a vehicle.

## CTRV Motion Model
CTRV model is a proper choice for this problem. 
<p align="center">
<img width="600" height="400" src="https://github.com/Badri-R-S/UKF_sensor_fusion/blob/master/Results/CTRV.png"
</p> 
  
While more complex models exist to capture highly dynamic behaviors, the CTRV strikes a balance between simplicity and accuracy. 
It provides a reasonable approximation of the motion dynamics for many real-world scenarios without introducing unnecessary complexity.
The way the state variables change under this dynamics model is described by the matrix below:
<p align="center">
<img width="600" height="400" src="https://github.com/Badri-R-S/UKF_sensor_fusion/blob/master/Results/CTRV_vec.png"
</p> 

## Steps to run the code
- The simulator can be downloaded from this link : [Simulator](https://github.com/udacity/self-driving-car-sim/releases/)
- The dependencies can be installed by simply running the **install-linux.sh** file that has been provided in the repository.
- You can build the workspace by running the following commands from the root of the workspace run:
  -  **mkdir build && cd build**
  -  **cmake .. && make**
- To run the program, make sure to have opened the simulator and have built the workspace. Then run **./UnscentedKF** in the build directory.

## Results:
- The Lidar measurements are shown as red circles, radar measurements are blue circles with an arrow pointing in the direction of the observed angle, and estimation markers are green triangles.
<p align="center">
<img width="600" height="400" src="https://github.com/Badri-R-S/UKF_sensor_fusion/blob/master/Results/result.png"
</p> 
  
- the full video can be viewed at : [Result](https://drive.google.com/file/d/1hQf3CVVo7QOwpajOerR6otkmzJUFUpog/view?usp=sharing)
