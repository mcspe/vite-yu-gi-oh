<script>
import {store} from '../data/store.js';
import Card from './partials/Card.vue'

export default {
  name: "Main",
  components:{
    Card,
  },
  data(){
    return{
      store
    }
  }
}
</script>

<template>
  <main>
    <div class="container">
      <div class="select-container w-25 mx-auto py-5">
        <select class="form-select" aria-label="Default select example">
          <option selected>Select a type</option>
        </select>
      </div>
      <div class="ms-card-container bg-white pt-5 px-5">
        <div class="ms-counter bg-dark text-white p-3">
          <span class="fs-3">Found {{store.resultArray.length}} cards</span>
        </div>
        <div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-5">
          <Card
            v-for="card in store.resultArray"
            :key="card.id" 
            :name="card.name"
            :type="card.archetype || card.type"
            :img="card.card_images"
            />
        </div>
      </div>
    </div>
  </main>
</template>

<style lang="scss" scoped>
  main{
    background: #D48F38;
  }
</style>