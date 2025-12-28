# Color-Picker-using-open-cv
A Python-based OpenCV project that implements an interactive RGB color picker using trackbars, enabling real-time color visualization and dynamic pixel updates.


import pandas as pd

import matplotlib.pyplot as plt

import cv2
import numpy as np
 
def function_R(x):
    pass
    # print(x)
    # global img
    # img[:,:,:]=[x,0,0]
    # cv2.imshow("Color Picker", img)

img=np.zeros((500,400,3),np.uint8)*255

cv2.namedWindow("Color_Picker")
 
cv2.createTrackbar("R","Color_Picker",0,255,function_R)
cv2.createTrackbar("G","Color_Picker",0,255,function_R)
cv2.createTrackbar("B","Color_Picker",0,255,function_R)

while True:
    
    cv2.imshow("Color_Picker",img)
    if cv2.waitKey(1) & 0xFF== ord('q'):
        break
    r=cv2.getTrackbarPos("R","Color_Picker")
    g=cv2.getTrackbarPos("G","Color_Picker")
    b=cv2.getTrackbarPos("B","Color_Picker")

    img[:,:,:]=[b,g,r]
    
    
cv2.destroyAllWindows()     





