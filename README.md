# Hand-Gesture-Tensorflow

Simple Python project using numpy , tensorflow , cv2 and mediapipe to recognise some gestures as stop,
rock , thumbs up , thumbs down etc .


mp.solutions.hands module performs the algorithm which recognises the hand gestures.

I configured the module to detect only one hand and the confidence to match the hand. The drawing_utils
draws the main keypoints that it could recognise the hand gesture.


Using tensorflow loaded a training dataset as mp_hand_gesture , printed the names of all gestures...
[‘okay’, ‘peace’, ‘thumbs up’, ‘thumbs down’, ‘call me’, ‘stop’, ‘rock’, ‘live long’, ‘fist’, ‘smile’]


Used the cv2 to open VideoCapture default webcam to read each frames and set the frames flipping it and
exit key on exiting it releases the webcam and detroy all windows opened by the code.


MediaPipe works only for rgb but the cv2 reads in bgr so I had to change the color scheme. If the code detects
multiple hand key points it stores the coordinate in a list ; the coordinates the changed from their normalised form
and drawn on the frame by draw_landmarks()


model.predict() returns an array containing 10 prediction classes out of which I took the max by numpy library
printed the className of the maximum predicted value ont he cv2 screen by cv2.putText function....
