<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Platform</ion-title>
      </ion-toolbar>
    </ion-header>
    
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Platform</ion-title>
        </ion-toolbar>
      </ion-header>
    
      <ion-list>
        <ion-item v-for="item in items" :key="item">
          <ion-label>{{ item.name }}</ion-label>
          <ion-icon slot="end" :icon="checkmarkSharp" class="yes" v-if="item.value"></ion-icon>
          <ion-icon slot="end" :icon="closeSharp" class="no" v-else></ion-icon>
        </ion-item>
      </ion-list>
    </ion-content>
  </ion-page>
</template>


<script lang="ts">

import { isPlatform, IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonList, IonItem, IonLabel, IonIcon } from '@ionic/vue';
import { checkmarkSharp, closeSharp } from 'ionicons/icons';
import { defineComponent } from 'vue';

export default defineComponent({
  components: { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonList, IonItem, IonLabel, IonIcon },

  data() {
    return {
      checkmarkSharp,
      closeSharp,
      items: [
        { name: 'android',   value: isPlatform('android') },
        { name: 'capacitor', value: isPlatform('capacitor') },
        { name: 'cordova',   value: isPlatform('cordova') },
        { name: 'desktop',   value: isPlatform('desktop') },
        { name: 'electron',  value: isPlatform('electron') },
        { name: 'hybrid',    value: isPlatform('hybrid') },
        { name: 'ios',       value: isPlatform('ios') },
        { name: 'ipad',      value: isPlatform('ipad') },
        { name: 'iphone',    value: isPlatform('iphone') },
        { name: 'mobile',    value: isPlatform('mobile') },
        { name: 'mobileweb', value: isPlatform('mobileweb') },
        { name: 'phablet',   value: isPlatform('phablet') },
        { name: 'pwa',       value: isPlatform('pwa') },
        { name: 'tablet',    value: isPlatform('tablet') },
      ],
    };
  },
});

</script>


<style scoped>
.yes {
  color: green;
}

.no {
  color: red;
}
</style>