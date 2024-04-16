<script>
import axios from 'axios';

export default {
  data() {
    return {title:"frontend"};
  },

  // appena l'app e' logicamente pronta
  created() {
    console.log(axios);
  },
};
</script>


<template>
  <div class="container mt-5"></div>

  <h1>{{ title }}</h1>
</template>

<style lang="scss">
@use '/src/scss/general.scss';
</style>