## Cubepilot-Here3-firmware

This repo was created because we needed IMU data from the here3, but the original firmware doesnt publish IMU data to dronecan.

Basically it just adds an imu update task to publish imu data over dronecan

To build firmware:

1. `git submodule update --init --recursive`
2. ensure the framework submodule is in the correct branch for imu development (should be another fork)
3.  `make BOARD_DIR=boards/com.hex.here_3.0`

To upload to the here3:

1. Connect the here3 to CAN1 port on Ardupilot
2. Go to the dronecan tab in mission planner setup and select CAN1
3. Right click on the here3 device and select update
4. Select no to the check updates online
5. Select the generated .bin file that has crc in its name
6. Check in the inspector if IMU data is being published
7. Profit