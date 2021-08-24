<template>
  <div>
    <personajes />
  </div>
</template>

<script>
import Personajes from './components/Personajes.vue';

export default {
  name: 'App',
  components : { Personajes },
  data: ()=>({
    
  }),
  methods: {},
}
</script>

<style>
  html, body{
    width: 100vw;
    height: 100vh;
    margin: 0;
    padding: 0;  
    background-color: black;
  }
</style>
