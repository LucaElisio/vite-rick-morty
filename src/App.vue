<script>
import axios from "axios"
import CardList from './components/CardList.vue';
import AppSearch from './components/AppSearch.vue';
import { store } from "./store";

export default {
  components: { 
    CardList,
    AppSearch,
  },
  data() {
    return {
      characterArray: [],
      store,
    };
  },
  created() {
    axios.
    get("https://rickandmortyapi.com/api/character")
    .then((resp) => {
      console.log(resp)
      this.characterArray = resp.data.results;
    });
  },
  methods: {
    showChar(){
      // console.log("ciao");
      console.log(this.store.selectedStatus);

      // Setto i parametri per la chiamata tramite axios
      const paramsObj = {
        status: ""
      }

      // Applico il filtro
      if (this.store.selectedStatus !== "All") {
        paramsObj.status = this.store.selectedStatus;
      }

      // Eseguo chiamata axios
      axios.
      get("https://rickandmortyapi.com/api/character", {
        params: paramsObj
      })
      .then((resp) => {
      console.log(resp)
      this.characterArray = resp.data.results;
    });

    }
  }
};
</script>

<template>
  <h1>Rick and Morty App</h1>
  <AppSearch @statusChanged="showChar"/>
  <CardList :characterArray="characterArray"/>
  <!-- <ul>
    <li v-for="curChar in characterArray">{{curChar.name}}</li>
  </ul> -->
</template>

<style scoped>
h1 {
  padding: 50px 0;
  text-align: center;
}
</style>
