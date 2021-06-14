# Drowsiness detection with OpenCV on Raspberry Pi.

Drowsy Driver Detection Using Raspberry Pi and Pi cam

## NOTE

This code can be run on laptop webcam , but It is intended to be used on Respberry Pi with Picam Module.

### Prerequisites

numpy</br>
dlib</br>
imultis(to test it in pc)</br>
OpenCv ( a tedious task to install it on rpi)</br>
picamera</br>
Rpi.GPIO if you need a alarm/buzzer

## Details
1. **The drowsiness detector algorithm:**
   1.	Search for face. In the camera Stream</br>
   ![Example Easy Face Detection](https://github.com/mdalmas/RpiDrowsyDriver/blob/master/eg2.jpg)
   2.	If a face is found, we apply facial landmark detection and extract the eye regions.
   3.   Now that we have the eye regions, we can compute the eye aspect ratio. If it is less than the a</br> certain threshold for a certain number of frames then we trigger the alarm.
   ![Example 2 Eye Aspect Ratio Plot](https://github.com/mdalmas/RpiDrowsyDriver/blob/master/eg1.jpg)
2. **Calculating Eyes Aspect Ratios**
   1.	The Haar cascade with 68 landmarks Face detector will give us Coordinates for the eye regeion.
   ![Example 3 Facilal](https://github.com/mdalmas/RpiDrowsyDriver/blob/master/eg3.jpg)
   2.	we can then use euclidean distance to calculate the 2 vertical and 1 horizontal distance.  
3. **Detecting Drowsiness Details**
   1.   After getting EA
   <code> 
    if ear < EYE_AR_THRESH:
        COUNTER += 1			
			if COUNTER >= EYE_AR_CONSEC_FRAMES:
				# if the alarm is not on, turn it on
				if not ALARM_ON:
					ALARM_ON = True  
    </code>
    
  
4. **RESULT**
   1. This is by no means perfect, </br> but combine it with pressure sensors on the steering and we may get a production class saftety device.
   2. Demonstration</br>
   ![The low res video ](https://github.com/mdalmas/covid19_xray_detection/blob/master/converted.mp4)

### Using

```python pi_detect_drowsiness.py --cascade haarcascade_frontalface_default.xml --shape-predictor shape_predictor_68_face_landmarks.dat --alarm 1

```



