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