<template >
  <div id="app">
  <div class="ion-page">
    <ion-header>
      <ion-toolbar>
        <ion-title style="text-align: center">Book manager</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content class="ion-padding">
      <Books></Books>
      <modal></modal>
    </ion-content>
  </div>
  </div>
</template>

<script>

  import Books from "./components/Books.vue"
  import modal from "./components/modal.vue"

  export default {
    name : 'app',
    components : {
      Books,modal
    },
  }
</script>