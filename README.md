
# RpiDrowsyDriver
Drowsy Driver Detection Using Raspberry Pi and Pi cam
Install NumPy, dlib, OpenCV, imutils and "picamera[array]"
Install RPi.GPIO and gpiozero if you are using a buzzer (In this code buzzer is used at gpio 15)
Installing Dlib and Open CV is tricky in Rpi so follow a tutorial
then on Command line (raspbian) workon cv 
python pi_detect_drowsiness.py --cascade haarcascade_frontalface_default.xml \--shape-predictor shape_predictor_68_face_landmarks.dat --alarm 1
