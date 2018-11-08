# picamerascikit
PI Camera basics and SCIKIT image examples

## Free up space
```
sudo apt-get purge wolfram-engine libreoffice* 
sudo apt-get clean
sudo apt-get autoremove

```

## Software installation
```bash
sudo apt-get install ipython3
sudo pip3 install jupyter
sudo pip3 install numpy
sudo pip3 install --no-cache-dir   matplotlib
sudo pip3 install scikit-video
sudo pip3 install -U scikit-image
sudo pip3 install scikit-learn
```
## Default on the PI
PI Camera

`import picamera`

## Import scikit-image

```python
import skimage 
print(skimage.__version__)
```

## Get an image from PiCamera into Skimage

```python
from picamera import PiCamera
from gpiozero import Button, LED
from datetime import datetime
from signal import pause

from skimage import color, io, img_as_uint, img_as_float
import numpy as np

led = LED(17)
button = Button(2)

#Deprecated in favor of default imageio plugin
#io.use_plugin('freeimage')


cam = PiCamera()
cam.resolution = (320, 240)
cam.framerate = 30

def capture():
    led.on()
    dt =datetime.now().isoformat()
    image  = np.empty((240, 320, 3), dtype=np.uint8)
    cam.capture(image,'rgb')
    image = color.rgb2gray(image)
    image = img_as_uint(image)
    io.imsave('iosave.png', image)
    led.off()


button.when_pressed = capture
pause()
cam.close()

```
## Picamera DOCS:

https://picamera.readthedocs.io/en/release-1.13/

## scikit-image skimage docs

http://scikit-image.org


## Arg. Fix for pip3 error
```
sudo apt-get purge -y python3-pip
wget https://bootstrap.pypa.io/get-pip.py
sudo python3 ./get-pip.py
sudo apt-get install python3-pip
```
