<template>
  <div id="container">
    <video ref="videoPlayer" class="video-js"></video>   
  </div>
</template>


<script>
  import videojs from 'video.js';
  import { registerIVSTech } from 'amazon-ivs-player';
  import 'video.js/dist/video-js.css';
  export default {
    name: 'VideoPlayer',
    props: {
      name: String
    },
    data: () => ({
      player: null,
      videoSource: process.env.VUE_APP_PLAYER_URL,
      videoOptions: {
        autoplay: true,
        controls: true,
        techOrder: ["AmazonIVS"],
        width: "800"
      },
    }),
    mounted() {
      // register the tech with videojs
      console.log(`wasmWorker: ${this.createAbsolutePath('/assets/amazon-ivs-wasmworker.min.js')}`)
      registerIVSTech(videojs,  {
        wasmWorker: this.createAbsolutePath('/assets/amazon-ivs-wasmworker.min.js'),
        wasmBinary: this.createAbsolutePath('/assets/amazon-ivs-wasmworker.min.wasm'),
      });
      // Init the player
      this.player = videojs(this.$refs.videoPlayer, this.videoOptions, () => {
        console.log('Player is ready to use!');
        // play the stream
        this.player.src(this.videoSource);
      })
    },
    beforeUnmount() {
      // Destroy the player instance
      if(this.player) {
        this.player.dispose();
      }
    },
    methods: {
      createAbsolutePath(assetPath) {
        console.log( document.URL );
        return new URL(assetPath, document.URL).toString();
      },
    }
  }
</script>

<style scoped>
#container {
  display: flex;
  justify-content: center;
  align-content: center;
  text-align: center;
  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
}
</style>