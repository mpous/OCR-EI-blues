
# OCR Reader using Edge Impulse Linux SDK and BalenaOS

This project is using an OCR ML model from Edge Impulse to read digits (from 0-9) through a camera. Once the digit is detected is going to be send a message using Blues Wireless.

![Testing OCR Reader](https://user-images.githubusercontent.com/173156/173465671-19ae4bc4-56ad-43c7-ae03-102ab2c73fec.png)

I'm using the model published on Edge Impulse [here](https://studio.edgeimpulse.com/public/18079/latest)


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

### How it works?

1. Create your Blues Wireless account on the [notehub.io](https://notehub.io)
2. Get your projectID and fileID
3. Clone the Edge Impulse OCR project on your Edge Impulse account from [here](https://studio.edgeimpulse.com/public/18079/latest)
4. Get your API key from Edge Impulse
5. Deploy with balena the project as explained above
6. Paste the variables `productID`, `fileID`, `EI_API_KEY` and the project might work.


