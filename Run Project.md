# **Project sumamry and how to run it :**

The code and results
Find the results graphs and videos in folder images above with some fail trials videos as I am trying to tune the pid to have final 2 accepted but not so good trials.

Find the codes used exists separtly as named main.cpp , pid_controller.cpp and pid_controller.h. it is possible to take those codes content to copy in Udacity workspace instead of exist codes and run or follow installation method to have same results.

**-> Installation**

Run the following commands to install the starter code in the Udacity Workspace:

**-> Clone the repository:**

git clone https://github.com/Shenhapy/Udacity_Control-and-Trajectory-Tracking_project.git

**-> Run Carla Simulator**

Open new window

* su - student // Will say permission denied, ignore and continue
* cd /opt/carla-simulator/
* SDL_VIDEODRIVER=offscreen ./CarlaUE4.sh -opengl

**-> Compile and Run the Controller**

Open new window

* cd Udacity_Control-and-Trajectory-Tracking_project/project
* ./install-ubuntu.sh
* cd pid_controller/
* rm -rf rpclib
* git clone https://github.com/rpclib/rpclib.git
* cmake .
* make (This last command compiles your c++ code, run it after every change in your code)

**-> Testing**

To test your installation run the following commands.

* cd Udacity_Control-and-Trajectory-Tracking_project/project
* ./run_main_pid.sh This will silently fail ctrl + C to stop
* ./run_main_pid.sh (again) Go to desktop mode to see CARLA

If error bind is already in use, or address already being used

* ps -aux | grep carla
* kill id
