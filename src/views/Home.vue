<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Jeux Olympiques</ion-title>
      </ion-toolbar>
      <ion-toolbar>
        <ion-searchbar placeholder="Rechercher un sport" showCancelButton="focus" @ionInput="ionInput($event.target.value)" cancel-button-text="Retour" animated></ion-searchbar>
      </ion-toolbar>
    </ion-header>
    <ion-content>
      <ion-list>
        <ion-item v-for="sport of sports" :key="sport.id">{{ sport.name }}</ion-item>
      </ion-list>
    </ion-content>
  </ion-page>
</template>

<script>
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonSearchbar, IonList, IonItem } from '@ionic/vue';

export default {
  name: 'Accueil',
  components: {
    IonContent,
    IonHeader,
    IonPage,
    IonTitle,
    IonToolbar,
    IonSearchbar,
    IonList,
    IonItem
  },
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
        },
        {
          id: 3,
          name: '4x400m (F)'
        },
        {
          id: 4,
          name: 'Poids (H)'
        },
        {
          id: 5,
          name: 'France - Slovénie (Basket H)'
        },
        {
          id: 6,
          name: 'Boxe - moins de 60 kg (F)'
        },
        {
          id: 7,
          name: 'Canoë-kayak - K1 200m (H)'
        },
        {
          id: 8,
          name: 'Omnium (H)'
        },
        {
          id: 9,
          name: 'Keirin (F) Demi-finales'
        },
        {
          id: 10,
          name: 'Australie - États-Unis (Football F)'
        }
      ]
    }
  },
  methods : {
    ionInput(value){
      const items = document.querySelectorAll('ion-item');
      const convertValue = value.normalize('NFD').replace(/[\u0300-\u036f]/g, "").toLowerCase();
      items.forEach(item => {
        const convertItemValue = item.textContent.normalize('NFD').replace(/[\u0300-\u036f]/g, "").toLowerCase();
        const shouldShow = convertItemValue.indexOf(convertValue) > -1;
        item.style.display = shouldShow ? 'block' : 'none';
      });
    }
  }
};
</script>