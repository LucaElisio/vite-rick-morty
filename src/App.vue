<script>
import axios from "axios"

export default {
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
  <!-- <ul>
    <li v-for="curChar in characterArray">{{curChar.name}}</li>
  </ul> -->
</template>

<style scoped>
h1 {
  margin-top: 20px;
  text-align: center;
}
</style>
