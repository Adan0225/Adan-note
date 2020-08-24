# 11.3 get IP camera test

```python
import cv2
import os

dirname = 'myfolder'
cap = cv2.VideoCapture("rtsp://admin:3mZHkBbp@192.168.10.155:554/live1.sdp");
print(cap.isOpened())

count = 0
while(cap.isOpened()):
    ret, frame = cap.read()
    if not ret:
        break
    else:
        cv2.imshow('frame', frame)
        #The received "frame" will be saved. Or you can manipulate "frame" as per your needs.
        name = "rec_frame"+str(count)+".jpg"
        cv2.imwrite(os.path.join(dirname,name), frame)
        count += 1
    if cv2.waitKey(20) & 0xFF == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

