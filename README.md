
# OCR Reader using Edge Impulse Linux SDK and BalenaOS

This project is using an OCR ML model from Edge Impulse to read digits (from 0-9) through a camera. Once the digit is detected is going to be send a message using Blues Wireless.


### Hardware 

* Raspberry Pi 4
* [Raspberry Pi camera](https://www.raspberrypi.org/products/camera-module-v2/) or any USB camera.

### Software 

* Sign up for a free [Edge Impulse account](https://edgeimpulse.com/)
* Sign up for a free [BalenaCloud account](https://www.balena.io/)
* [balenaEtcher](https://www.balena.io/etcher/)

### Deploy using balenaCloud

Click on the *deploy-with-balena* button as given below, which will help you to deploy your application to balenaCloud and then to your Raspbery Pi in **one-click!**

[![](https://balena.io/deploy.png)](https://dashboard.balena-cloud.com/deploy?repoUrl=https://github.com/mpous/OCR-EI-blues)

Else you can build your own release by cloning this repo on your primary machine (x86) and use the following commands :
```
$ git clone https://github.com/mpous/OCR-EI-blues.git
$ cd OCR-EI-blues
$ balena login
$ balena push OCR-EI-blues 
```

