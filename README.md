# Control-and-Trajectory-Tracking-for-Autonomous-Vehicles
## **Task :**
* Build the PID controller object
* PID controller for throttle
* PID controller for steer
* Evaluate the PID efficiency
#
The following video displays the result of implementing the above steps where the car was able to drive through the obstacles placed throughout the street. Understanding the the **P**, **I**, and **D** in **'PID'** allowed the ability to better tune the controller gains.

![gif_1](https://github.com/DishaJr/Control-and-Trajectory-Tracking-for-Autonomous-Vehicles/blob/main/ezgif.com-video-to-gif%20(3).gif)
#
The process of going through several trials resulted in achieving the following values as the gains for the controller.

**The values of steering gains :**
* P = 0.5
* I = 0.0005
* D = 0.0007

**The values of throtle gains :**
* P = 0.2
* I = 0.0005
* D = 0.001

![graph_1](https://github.com/DishaJr/Control-and-Trajectory-Tracking-for-Autonomous-Vehicles/blob/main/Screenshot%20from%202023-05-05%2018-52-05.png)
![graph_2](https://github.com/DishaJr/Control-and-Trajectory-Tracking-for-Autonomous-Vehicles/blob/main/Screenshot%20from%202023-05-05%2018-53-13.png)
#
## **Questions :**
**1- Add the plots to your report and explain them :**

The first figure displays the data gathered from the steering control, it can be seen that the vehicle exibits steep transition from one side to the other ( steep oscillation ). The values of the PID are selected in a matter that the largest value was given to proportional, as we require the vehicle to be roughly aligned with the curvature of the goal trajectory to avoid obstacles. The next weight was given to the derivative as it is needed to keep the steering response values within reasonable limits. The value of the integaral is set in which it is attempted to penalise the cumulative uncorrected steering error in a consecutive time interval.

The second figure displays the data gathered from the throttle control, it can be observed that the error from the controllr stabilizes to a steady state after the initial rise time. The graph shows that the controller maintained a high value throught most of the session, however a gradual decrease of the throttle error is seen. It can be concluded that the overall throttle response is effectively tuned than the steering controller.

**2- What is the effect of the PID according to the plots? How does each part of the PID effect the control command? :**

The proportional gain determines how much the controller responds to the current error as it amplifies the signal. A high value causes the controller to respond aggressively to the error, on the other hand it may cause overshooting and instability.

The integral gain determines how the controller responds to the accumulated error over time and eliminates steady-state error signal. A high value causes the controller to respond aggressively to long-term errors, but may cause instability and oscillation.

The derivative gain determines how the controller responds to the rate of change of the error through adding a term proportional to the derivative of the error signal to minimize overshoot and oscillation. A high value causes the controller to respond aggressively to sudden changes in the error, however it may also cause instability and overshooting.

**3- How would you design a way to automatically tune the PID parameters? :**

Twiddle would be a great solution as it would iterate throught the code to find the best values for the PID controller, minimizing the error.

**4- PID controller is a model free controller, i.e. it does not use a model of the car. Could you explain the pros and cons of this type of controller? :**

An advantage of the PID controller is that it is easy to comprehend and be used many systems. On the other side it is difficult to tune resulting in low accuracy.
