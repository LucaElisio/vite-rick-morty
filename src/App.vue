<script>
import axios from "axios"
import CardList from './components/CardList.vue';

export default {
  components: { 
    CardList 
  },
  data() {
    return {
      characterArray: [],
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
};
</script>

<template>
  <h1>Rick and Morty App</h1>
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
