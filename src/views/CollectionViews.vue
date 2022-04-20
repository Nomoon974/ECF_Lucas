<template>
  <!-- Main Wrapper -->
  <div id="main-wrapper">
    <div class="wrapper style2">
      <div class="inner">
        <div class="container">
          <div id="content">

            <!-- Content -->

            <article>
              <header class="major">
                <h2>Ma Collection</h2>
              </header>
              <div class='card-list' v-for="carte in collec.cards" :key="carte.id">
                <div class='card-title'><b> {{ carte.number }} </b> {{ carte.name }} </div>
                <div @click="goToDetails(carte.id)" class='card-action'>👀</div>
              </div>

            </article>

          </div>
        </div>
      </div>
    </div>

  </div>
</template>

<script>
import axios from 'axios';
const COLLECTION_LIST = "https://api.magicthegathering.io/v1/cards";

export default {
  name: "CollectionViews.vue",
  data:()=>({
    collec: [],

  }),
  methods: {
    goToDetails(id) {
      this.$router.push({name: 'card-details', params: {cardNum:id}})
    }

  },
  async created(){
    const collec = await axios.get(COLLECTION_LIST)
    this.collec  = collec.data

  }
}
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css?family=Open+Sans:400,400italic,700,800");
@import '@/assets/css/main.css';
@import '@/assets/css/card-list.css';

.card-action{
  cursor: pointer;
}

</style>