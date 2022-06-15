
# OCR Reader using Edge Impulse Linux SDK and BalenaOS

This project is using an OCR ML model from Edge Impulse to read digits (from 0-9) through a camera. Once the digit is detected is going to be send a message using Blues Wireless.

![Testing OCR Reader](https://user-images.githubusercontent.com/173156/173465671-19ae4bc4-56ad-43c7-ae03-102ab2c73fec.png)

I'm using the model published on Edge Impulse [here](https://studio.edgeimpulse.com/public/18079/latest)


### Hardware 

* Raspberry Pi 4
* [Raspberry Pi camera](https://www.raspberrypi.org/products/camera-module-v2/) or any USB camera.
* [Notecarrier Pi Hat](https://shop.blues.io/products/carr-pi)
* [Notecard](https://shop.blues.io/products/note-nbgl-500)

### Software 

* Sign up for a free [Edge Impulse account](https://edgeimpulse.com/)
* Sign up for a free [BalenaCloud account](https://www.balena.io/)
* Sign up for the [Notehub account](https://notehub.io)
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

<img width="1884" alt="Notehub" src="https://user-images.githubusercontent.com/173156/173960131-a72b1bae-38ff-4bbc-a117-c8f678391fd1.png">

2. Create a new Project on Notehub and get your `projectID` and `fileID`:

![Create a blues project](https://user-images.githubusercontent.com/173156/173959908-b274bfb5-2952-4a00-82ce-5b0e42e90e84.png)

![Project created at notehub](https://user-images.githubusercontent.com/173156/173960368-eedc9e5a-2a9f-44db-a311-97ab13e19975.png)

Remember to copy the `projectID`.

3. Clone the Edge Impulse OCR project on your Edge Impulse account from [here](https://studio.edgeimpulse.com/public/18079/latest)



4. Get your API key from Edge Impulse


6. Deploy with balena the project as explained above

7. Paste the variables `ENABLE_BLUES_WIRELESS` to `Y`, then `productID`, `fileID`, `EI_API_KEY` and the project might work.


