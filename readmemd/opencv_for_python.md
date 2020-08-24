# 9.6 opencv for python

圖像矩陣的shape屬性表示圖像的大小，shape會返回tuple元組，第一個元素表示矩陣行數，第二個元組表示矩陣列數，第三個元素是3，表示像素值由光的三原色組成。

```python
import cv2
import numpy as np
fn="baboon.jpg"
if __name__ == '__main__':
    print 'load %s as ...' % fn
    img = cv2.imread(fn)
    sp = img.shape
    print sp
    sz1 = sp[0]#height(rows) of image
    sz2 = sp[1]#width(colums) of image
    sz3 = sp[2]#the pixels value is made up of three primary colors
    print 'width: %d \nheight: %d \nnumber: %d' %(sz1,sz2,sz3)
```

