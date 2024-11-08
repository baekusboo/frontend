<template>
  <img alt="wonders-of-the-world" src="https://www.worldatlas.com/upload/9e/4e/a3/7-wonders-of-the-world-005.jpeg" width="800" height="500">
  <WonderCard :wonders="wonders" />
</template>

<script>

import WonderCard from './components/WonderCard.vue';

export default {
  name: 'App',
  components: {
    WonderCard
  },
  data(){
    return {
      wonders: []
    }
  },
  methods:{
    //promoises
    async fetchwonders(){

      try {
      const res = await fetch('https://wondersoftheworldbackend.vercel.app/api');
      const data = await res.json();
      console.log(data);
      return data;
      } catch (error) {
        console.error("Error fetching wonders:", error);
      }
    }
  },
  async created(){
      this.wonders = await this.fetchwonders();
  }
}
</script>

<style>

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>