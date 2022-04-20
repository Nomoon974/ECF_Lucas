<template>
  <!-- Main Wrapper -->
  <div id="main-wrapper">
    <div class="wrapper style2">
      <div class="inner">
        <div class="container">
          <div class="row">
            <div class="col-8 col-12-medium">
              <div id="content">

                <!-- Content -->

                <article>
                  <header class="major">
                    <h2>{{ details.name }}</h2>
                    <p>{{ details.artist }}</p>
                  </header>

                  <span class="image featured">
														<img src="http://gatherer.wizards.com/Handlers/Image.ashx?multiverseid=130550&type=card" alt="" />
													</span>

                  <p>{{ details.originalText }}</p>
                </article>

              </div>
            </div>
            <div class="col-4 col-12-medium">
              <div id="sidebar">

                <!-- Sidebar -->

                <section>
                  <header class="major">
                    <h2>Infos</h2>
                  </header>
                  <p>set name: <b>{{ details.setName }}</b></p>
                  <p >rarity:  <b> {{ details.rarity }} </b></p>
                  <p >toughness:  <b> {{ details.toughness }} </b></p>

                  <span class="button alt icon ">
														{{ details.power }}
														<i class="fa-solid fa-fire-flame-curved"></i>
														<i class="fa-solid fa-fire-flame-curved"></i>
														<i class="fa-solid fa-fire-flame-curved"></i>
													</span>
                </section>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

  </div>
</template>

<script>
import axios from 'axios'
require('@/assets/css/main.css')
require('@/assets/css/card-list.css')


export default {
  name: "CardDetailsViews.vue",
  data:() => ({
    details: {}
  }),
  async created() {
    const {cardNum} = this.$route.params
    const apiDetails = 'https://api.magicthegathering.io/v1/cards/'+cardNum
    const oneCard = await axios.get(apiDetails)
    this.details = oneCard.data.card
    console.log(oneCard)
  }
}
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css?family=Open+Sans:400,400italic,700,800");
@import '@/assets/css/main.css';
@import '@/assets/css/card-list.css';


</style>