Ros-i2cpwmboard is the project for the i2cpwm_board controller node by http://bradanlane.gitlab.io/ros-i2cpwmboard/

Viewing documnetation, clone the repo and open the index.html file in a browser with in repo at location

doc/html/index.html

All credits to:

Forked project from gitlab to github: gitlab.com/bradanlane/ros-i2cpwmboard

Controller for I2C interfaced 16 channel PWM boards with PCA9685 chip
Bradan Lane Studio info@bradanlane.com
Copyright (c) 2016, Bradan Lane Studio
Licensed under GPLv3


# FILE STRUCTURE AND CODE

The file is broken into sections:

private properties (all private properties have a leading underscore)
private methods (all private methods have a leading underscore)

public topic subscribers:
servos_absolute()
servos_proportional()
servos_drive()

public services:
set_pwm_frequency()
set_active_board()
config_servos()
config_drive_mode()
stop_servos()

The code is currently authored in C and should be rewritten as proper C++.

This documentation refers to 'servo' and 'RC servo' but is equally applicable to any PWM or PPM controlled DC motor.

All published services and topics use a one-based count syntax. For example, the first servo is '1' and the default board is '1'. The hardware uses zero-based values. For example the first channel on the 16 channel 12-bit PWM board is '0' and the first I2C board is '0' with address 0x40. The switch from one-based to zero-based is done at the lowest level of this code. All public interactions should assume one-based values.

WARNING: The code has only been tested with a single board using the default I2C address of 0x40. Once testing has been done with additional configurations, this warning will be removed or amended.
