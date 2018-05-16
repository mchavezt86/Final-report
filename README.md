# Final-report
Final report for 4B25

In this repository you will find the final report and the code used in the final coursework activity #6.

- 'Code composer' folder
- 'Evothings code' folder
- 'Final report.pdf' PDF file with 2 page report and annex

Description of contents:

'Code composer' contains the files modified from the TI Sensortag code provided by Texas Instrument, which means that this solution is based on its code for using the SensorTag in fully functional mode (app name: SensorTag)
The files in this folder:
- main.c
Contains the main program, but not much code modified, the important task: calls on of the sensortag.c function which is the main program of the SensorTag.
- sensortag.c
Contains the main program of the SensorTag and calls other programs to set up the sensors and actuators.
- sensortag.h
Header file of the previous file.
- sensortag_keys.c
Contains the main program for the keys of the SensorTag. For the solution provided, the main function is to set the reference and turn the led on when the right button is pressed.
- sensortag_keys.h
Header file of the previous file.
- sensortag_mov.c
Contains the main program for the movement sensor of the SensorTag and the main logic of the whole solution. The movement sensor is setup  to only use the accelerometer (3 axis, even when we use only one). While reading its value it also filters the data and process a linearisation based on arithmetic and bitwise operations. As an output it displays a light if the calculated difference angle from the reference, which is read when the right button is pressed, and the current angle is greater than a threshold.
- sensortag_mov.h
Header file of the previous file.

'Evothings code' contains the code of the Evothings solution.
- index.html
The important file as in contains the whole solution. The main logic is behind the "accelerometerHandler" function. Here the program reads the accelerometer values used for calculation and also applies a similar process to the SensorTag. First, applies a filter to the readed values, then use the Z axis to use the same linearisation as the SensorTag and displays the value in the smartphone. However, it also uses the Y axis to calculate the angle using arctan function and displays is on the smartphone. Similar to the SensorTag solution, as the user presses the SensorTag right button, the program stores the value calculated using arctan, and compare it with the current values. If the difference is higher than a threshold it changes the apps background color to red (effectively the whole smartphone screen).

Miguel Chavez
(mac225@cam.ac.uk)
