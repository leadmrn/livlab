<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Moteur de recherche</ion-title>
      </ion-toolbar>
      <ion-toolbar>
        <ion-searchbar placeholder="Rechercher un sport" showCancelButton="focus" animated></ion-searchbar>
      </ion-toolbar>
    </ion-header>
    <ion-content>
      <ion-list>
        <ion-item v-for="sport of sports" v-bind:key="sport.id">{{ sport.name }}</ion-item>
      </ion-list>
    </ion-content>
  </ion-page>
</template>

<script>
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonSearchbar, IonList, IonItem } from '@ionic/vue';
export default {
  name: 'Accueil',
  data(){
    return{
      sports: [
        {
          id: 1,
          name: 'Décathlon (H)'
        },
        {
          id: 2,
          name: '110m haies (F)'
        }
      ]
    }
  },
  handleChange(){
    console.log('cc')
  },
  components: {
    IonContent,
    IonHeader,
    IonPage,
    IonTitle,
    IonToolbar,
    IonSearchbar,
    IonList,
    IonItem
  }
};
</script>