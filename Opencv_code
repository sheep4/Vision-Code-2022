import numpy as np
import cv2

# sets up the cap variable
cap = cv2.VideoCapture(0)

while True:
    
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))

    # Sets up color threshold
    hsv = cv2.cvtColor(frame, cv2.COLOR_BGR2HSV)
    lower_yellow = np.array([20,100,100])
    upper_yellow = np.array([130, 255, 255])

    mask = cv2.inRange(hsv,lower_yellow, upper_yellow)

    result = cv2.bitwise_and(frame, frame, mask=mask)
        

    # makes windows
    cv2.imshow('frame', result)
    cv2.imshow('mask', mask)
    
    #Lets the window stay up & closes it when q is pressed
    if cv2.waitKey(1) == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
