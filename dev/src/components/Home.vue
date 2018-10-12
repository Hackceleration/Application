
<template>
  <v-ons-page>
    <v-ons-toolbar>
      <div class="center">MealCheck</div>
      <div class="left">
          <v-ons-toolbar-button icon="ion-navicon, material: md-menu"></v-ons-toolbar-button>
      </div>
    </v-ons-toolbar>

    <section style="margin: 16px">
      <v-ons-button modifier="large" style="margin: 6px 0">Large</v-ons-button>
    </section>

    <v-ons-card>
      <div class="title">
        Nom de la recette
      </div>
      <div class="content">
        <v-ons-list>
          <v-ons-list-header>Sous-Titre</v-ons-list-header>
          <v-ons-list-item>Description</v-ons-list-item>
        </v-ons-list>
      </div>
    </v-ons-card>
    
        <v-ons-card>
      <div class="title">
        Nom de la recette
      </div>
      <div class="content">
        <v-ons-list>
          <v-ons-list-header>Sous-Titre</v-ons-list-header>
          <v-ons-list-item>Description</v-ons-list-item>
        </v-ons-list>
      </div>
    </v-ons-card>
    
        <v-ons-card>
      <div class="title">
        Nom de la recette
      </div>
      <div class="content">
        <v-ons-list>
          <v-ons-list-header>Sous-Titre</v-ons-list-header>
          <v-ons-list-item>Description</v-ons-list-item>
        </v-ons-list>
      </div>
    </v-ons-card>
  </v-ons-page>

</template>

<script>
export default {
   name: 'camera',
  data () {
    return {
     
    };
  },
  computed: {
  },
  methods: {  
    md() {
      return this.$ons.platform.isAndroid();
    },
    takePicture() {
        if (navigator.camera) {
          navigator.camera.getPicture(this.setPicture, this.error, {});
        }else{
          // If the navigator.camera is not available display generic error to the user.
          this.error();
        }
      },
      // Set the picture path in the data of the vue
      // this action will automatically update the view.
      setPicture(imagePath){
        this.imagePath = imagePath;
      },
      error(){
        nativeAlert(this.$t("error"));
      }

  }
};
</script>

<style>

</style>
