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
##Default on the PI
PI Camera

`import picamera`

DOCS:

https://picamera.readthedocs.io/en/release-1.13/

## Arg. Fix for pip3 error
```
sudo apt-get purge -y python3-pip
wget https://bootstrap.pypa.io/get-pip.py
sudo python3 ./get-pip.py
sudo apt-get install python3-pip
```
