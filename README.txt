MyLastNight
===========

CS 196 Honors Project

Sensor Activity :
The sensor activity class uses the accelerometer to detect movement, and creates an instance of the CounterClass to cancel/ restart the timer . 
To use the accelerometer, first the SensorEventListener interface must be implemented.To do this I first call the getSystemService method with the parameter being the name of the service (in this case SENSOR_SERVICE) to get a reference to the service. Using this reference , I then get a reference to the System's accelerometer by calling getDefaultSensor method with the final variable TYPE_ACCELEROMETER. I then register the sensor.

The onStop() and onResume() methods are only used to unregister and register the sensor respectively. 

The onSensorChanged method is the most important method in this class. It firsts finds out the position of the device by extracting its x,y and z axis values. It also has a check that ensures the method is invoked every 100 milliseconds . It calculates the speed (change in movement) and then checks if its greater than the minimum speed defined in the main class. If it is, then it invokes the cancel method of the timer class, and restarts the timer. 
If not,it calls the onFinish function in the timer class .

CounterClass : 
CounterClass is a subclass of the CountDownTimer class in the android API. It has functions that can display the amount of time left, and has a function onFinish() that sets the alarm off and begins the quizzes.
