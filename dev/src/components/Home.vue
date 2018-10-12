
<template>
  <v-ons-page>
    <v-ons-toolbar class="titulo" modifier="material noshadow" style="position:relative">
        <div class="center">Check app</div>
        <div class="right">
          <v-ons-toolbar-button icon="ion-navicon, material: md-heart"></v-ons-toolbar-button>
          <v-ons-toolbar-button icon="ion-navicon, material: md-search"></v-ons-toolbar-button>
        </div>
    </v-ons-toolbar>
  </v-ons-page>
</template>

<script>


export default {
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
  }
};
</script>

<style>

</style>
