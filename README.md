# Pelican Dataset


As a part of a project in [WAVELab](http://wavelab.uwaterloo.ca/) on system identification and modeling of a quadrotor for Multi-Step prediction, a dataset was gathered. This page contains information about this dataset. The results of a Black-box and a Grey-box modeling will be also reported shortly.

(Maintained by [Nima Mohajerin](mohajerin.nima@gmail.com))

Format MATLAB .mat
Size  238.1 MB

Download here: [AscTec_Pelican_Flight_Dataset](http://wavelab.uwaterloo.ca/wp-content/uploads/2017/09/AscTec_Pelican_Flight_Dataset.mat)

## Information about dataset
### Vehicle
The AscTec Pelican is a light weight quadrotor. It is equipped with a real-time autopilot board coupled with an onboard computer running Ubuntu OS and communicates with the autopilot board via a UART connection. The ROS Indigo software running a suitable ROS node is used to collect the motor speeds and Inertial Measurement Unit (IMU) measurements. The vehicle is operated in an indoor environment by an expert pilot using a Futaba T7C remote control.

### Measurement system, data synchronisation and signals
Download this [documentation](https://github.com/wavelab/pelican_dataset/dataset/Pelican_Dataset.pdf).

### Description
The dataset contains 54 flights covering a wide range of regimes. The flights are stored as MATLAB cells with the following fields:

- len: The number of samples in the flight
- Pos: The position measurement (x, y, z) from Vicon, a 3-by-len matrix
- Euler: The orientation measurement (roll, pitch, yaw) from Vicon, a 3-by-len matrix
- Motors: The motors actual speed as reported by the ROS node, 4-by-len matrix
- Motors_CMD: The commanded motor speeds as reported by the ROS node, a 4-by-len matrix
- Vel: The calculated velocity (v_x, v_y, v_z) by applying a numerical difference on the position measurement, a 3-by-(len-1) matrix
- pqr: The calculated body rates (p, q, r) by applying a numerical difference on the Euler measurements and transferring them into the body frame, a 3-by-(len-1) matrix
