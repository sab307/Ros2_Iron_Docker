# ROS2 IRON DOCKER

A hack was used here.
Since rmw_zenoh isn't released for this version, humble branch was used.

'''
git clone this repo
git submodule init
git submodule update
source /opt/ros/iron/setup.bash
sudo apt update
'''

After running these commands, change all the CMakeFiles dealing with Zenoh to C++20 version instead of 17
'''
rosdep install -i -y --from-paths src --rosdistro iron
rosdep install -i -y --from-paths src --rosdistro humble
colcon build --packages-select usb_cam zenoh_cpp_vendor
'''

After this run,
'''
colcon build
'''
### ROS2 Iron Docker
video_device: "/dev/video0" in the usb_cam/config/ folder change that according to the web camera and save it in a separate file.

CAMERAS.append(
    CameraConfig(
        name='camera1',
        param_path=Path(USB_CAM_DIR, 'config', 'params_1.yaml')
    )
    # Add more Camera's here and they will automatically be launched below
)
change the name and param file name accordingly to add further camera's in the launch folder.