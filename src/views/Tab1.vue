<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Tab 1</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Tab 1</ion-title>
        </ion-toolbar>
      </ion-header>
    
      <VideoPlayer name="Tab 1 page" />
    </ion-content>
  </ion-page>
</template>
 
<script lang="ts">
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
import VideoPlayer from '@/components/VideoPlayer.vue';
 
export default  {
  name: 'Tab1',
  components: { VideoPlayer, IonHeader, IonToolbar, IonTitle, IonContent, IonPage }
}
</script>
