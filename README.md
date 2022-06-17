
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

### Step-by-step Tutorial

1. Create your Blues Wireless account on the [notehub.io](https://notehub.io)

<img width="1884" alt="Notehub" src="https://user-images.githubusercontent.com/173156/173960131-a72b1bae-38ff-4bbc-a117-c8f678391fd1.png">

2. Create a new Project on Notehub and get your `projectID` and `fileID`:

![Create a blues project](https://user-images.githubusercontent.com/173156/173959908-b274bfb5-2952-4a00-82ce-5b0e42e90e84.png)

![Project created at notehub](https://user-images.githubusercontent.com/173156/173960368-eedc9e5a-2a9f-44db-a311-97ab13e19975.png)

Remember to copy the `projectID`.

3. Clone the Edge Impulse OCR project on your Edge Impulse account from [here](https://studio.edgeimpulse.com/public/18079/latest)

<img width="1904" alt="Clone the Edge Impulse model" src="https://user-images.githubusercontent.com/173156/174340041-fc847414-3194-4932-8503-d95f4c7e9e77.png">

Press the button `Clone this repo` and then host it on your Edge Impulse account. 

4. Get your API key from your Edge Impulse project

<img width="1904" alt="Create a new API key" src="https://user-images.githubusercontent.com/173156/174340798-227b90ea-7148-425f-a16b-735760460243.png">

5. Deploy with balena the project clicking the button below if you already didn't do it

[![](https://balena.io/deploy.png)](https://dashboard.balena-cloud.com/deploy?repoUrl=https://github.com/mpous/OCR-EI-blues)

6. Once the fleet has been created on balenaCloud and the project deploying, click `Add Device`. Select the device you have (e.g. Raspberry Pi 4) and add the WiFi credentials from your router.

<img width="1904" alt="Add a device to your balenaCloud fleet" src="https://user-images.githubusercontent.com/173156/174341607-6a91c17c-0211-48ff-928c-30760a6a0bb9.png">


7. Download the balenaOS image and flash your SD card with [Etcher](https://www.balena.io/etcher/)

<img width="912" alt="Flash your SD card with balena Etcher" src="https://user-images.githubusercontent.com/173156/174341764-7bc7830f-354b-40ee-aee2-5eadf7fb091c.png">

8. Once the flashing process has completed, insert your SD card into the Raspberry Pi and connect the power supply.

9. Your device should get `Online` on the balenaCloud dashboard and the services deployed on each device of your fleet.

<img width="1904" alt="Device running on balenaCloud" src="https://user-images.githubusercontent.com/173156/174342190-7bf1b6a6-d12c-4c4c-ab9e-db362b79e5d1.png">

10. Go to `Device Variables` and add the variables `ENABLE_BLUES_WIRELESS` to `Y`. Overribe the `productID` with the productID from the noteHub, `fileID` (as `data.qo`). And paste the Edge Impulse API key as `EI_API_KEY`. At this moment, the device will restart and the project might work. 

11. Go to the local IP address of the device or click `Public Device URL` and you will be able to access to a local website rendering the camera stream.

<img width="1904" alt="Testing the OCR project" src="https://user-images.githubusercontent.com/173156/174343635-ec028860-607f-4f96-bee5-e3ca5dc1f060.png">

12. If everything worked well, it's the moment to check that the Edge Impulse model works well and Notehub is receiving properly the data. Go to `Events` and check the data that is being sent to the Notehub. If you don't receive any data here, it's time to go to the balenaCLoud Logs and check what error is being detected. To test, I usually write some numbers and test.

![Events received on the Blues Wireless Notehub](https://user-images.githubusercontent.com/173156/174343898-b4a0c5f5-aead-465f-89f2-21c1be6608ad.png)

13. Once the data is properly sent to the Notehub, it's time to send it to Datacake to visualize the digits being read by our edge device. Go to the Notehub `Routes` and Create a new Route.

![Create Routes](https://user-images.githubusercontent.com/173156/174343879-a0a98d70-73e6-4a90-a945-4849d924ec56.png)




