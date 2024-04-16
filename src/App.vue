<script>
import axios from 'axios';

export default {
  data() {
    return {title:"frontend",
    projects: [],
  };
  },

  // appena l'app e' logicamente pronta
  created() {
    axios.get('http://127.0.0.1:8000/api/projects').then((response)=>{
      this.projects = response.data.data;
      console.log(response.data.data);
    })
  },
};
</script>


<template>
  <div class="container mt-5">
    <h1>{{ title }}</h1>
    <div v-for="project in projects">
      <ul><strong>Numero Progetto:</strong> {{ project.id }}</ul>
      <ul><strong>Title:</strong> {{ project.title }}</ul>
      <ul><strong>Content:</strong> {{ project.content }}</ul>
      <ul><strong>Type:</strong> {{ project.type.label }}</ul>
      <hr>
    </div>

  </div>

</template>

<style lang="scss">
@use '/src/scss/general.scss';
</style>