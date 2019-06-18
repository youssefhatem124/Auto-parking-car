# Auto-parking-car
Auto-parking Car (Graduation project):
(STM32F429 Discovery board, Ultrasonic sensor, Camera module (OV7670), TFT-LCD ILI9341)
•	First, we learned how to control the car via the remote control and how to control the motors speed using PWM.
•	We started to wrap the right side of the car with 5 Ultrasonic sensors for full right side control according to distances.
•	When the car is in the required position for parking it moves forward , it passes by a car then an empty space then another car.
•	When it becomes parallel to the second car with a specific distance between the two of them, it starts steering the wheels to the right and moves backward till the right back corner sensor reaches the required distance.
•	Then it steers the wheels to the left and continues moving backwards till the back sensor reaches the required distance.
•	Then it steers the wheels to the right and starts moving forward till it reaches the required distance and at last it steers the wheels to the middle and stops moving.
•	This is all done while a camera is fixed on the back of the car to stream a live video on the TFT-LCD.
•	Used:
1.	RCC to configure the micro-processor to run at 90 MHZ.
2.	NVIC (Nested vector interrupt controller) to enable the peripherals interrupt.
3.	SCB (System control block) to adjust the group-priority to enable preemption.
4.	4 Channels of Timer 1 and 1 Channel of Timer 8 in ICU mode to capture the Pulse Width of the Ultrasonic sensor.
5.	4 Channels of Timer 2 in PWM mode to control 2 DC motors for forward and backward movement and 2 Servo motors for steering the wheels left and right.
6.	Timer 3 as a counter to calculate the distance between the two cars to decide whether the car can park or not.
7.	Timer 7 as a scheduler for the mini simplified-RTOS we implemented.
8.	GPIO to send a trigger to the 5 Ultrasonic sensors.
9.	SysTick as a delay timer.
10.	I2C to configure the Camera internal registers.
11.	DCMI (with DMA2) to capture the Camera frame.
12.	SPI5 to send the frame to the TFT-LCD. 

