# Hello IVS + Ionic-Vue

This is an [Ionic-Vue](https://ionic.io) & [Amazon IVS Player](https://docs.aws.amazon.com/ivs/latest/userguide/player.html) app with [Video.js](https://videojs.com/). It loads a stream channel into the player. 

Check the step by step tutorial [here](https://dev.to/superdiana/build-an-amazon-ivs-player-app-with-ionic-vue-1d20)

## Project setup

Install all dependencies

```
npm install
```

Create a `.env` file and set the value for the variable `VUE_APP_PLAYER_URL`

```
VUE_APP_PLAYER_URL='https://fcc3ddae59ed.us-west-2.playback.live-video.net/api/video/v1/us-west-2.893648527354.channel.DmumNckWFTqz.m3u8'
```

### Compiles and hot-reloads for development

```
ionic serve
```


### Build a Native App

Adding native functionality is easy. First, add Capacitor to your project: [capacitorjs](https://capacitorjs.com/)
```
ionic integrations enable capacitor
```
Build the project, then add your platform of choice:
```
ionic build
ionic cap add ios
ionic cap add android
```

We use the standard native IDEs (Xcode and Android Studio) to open, build, and run the iOS and Android projects:
```
ionic cap open ios
ionic cap open android
```

For more information
[ionic-vue documentation](https://ionicframework.com/docs/vue/quickstart#build-a-native-app)



## Test Streams

You can use these test streams provided by Amazon IVS

- 1080p30 - https://fcc3ddae59ed.us-west-2.playback.live-video.net/api/video/v1/us-west-2.893648527354.channel.DmumNckWFTqz.m3u8
- Square Video - https://fcc3ddae59ed.us-west-2.playback.live-video.net/api/video/v1/us-west-2.893648527354.channel.XFAcAcypUxQm.m3u8
- Vertical Video - https://fcc3ddae59ed.us-west-2.playback.live-video.net/api/video/v1/us-west-2.893648527354.channel.YtnrVcQbttF0.m3u8
- Quiz - https://fcc3ddae59ed.us-west-2.playback.live-video.net/api/video/v1/us-west-2.893648527354.channel.xhP3ExfcX8ON.m3u8
- VOD - https://d6hwdeiig07o4.cloudfront.net/ivs/956482054022/cTo5UpKS07do/2020-07-13T22-54-42.188Z/OgRXMLtq8M11/media/hls/master.m3u8

## Code Samples

You may find more code samples of Amazon IVS in the [official repository](https://github.com/aws-samples/amazon-ivs-player-web-sample).
