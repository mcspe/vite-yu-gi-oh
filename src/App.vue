<script>
  import axios from "axios";
  import {store} from "./data/store.js";
  import Header from "./components/Header.vue";
  import Main from "./components/Main.vue";
  import Footer from "./components/Footer.vue";
  export default{
    name: "App",
    components: {
      Header,
      Main,
      Footer
    },
    data(){
      return{
        store
      }
    },
    methods:{
      getApi(){
        axios.get(store.apiUrl, {
          params:{
            num: store.cardNumber,
            offset: store.cardOffset
          }
        })
        .then(result => {
          store.resultArray = result.data.data;
        })
      }
    },
    mounted(){
      this.getApi();
      console.log(store.resultArray);
    }
  }
</script>

<template>
  <Header titolo="Yu-Gi-Oh Api"/>
  <Main />
  <Footer />
</template>

<style lang="scss">
  @import "./scss/main.scss";
</style>
