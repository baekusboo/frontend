<template>

<div class="wonder-card-container">
    <div v-for="wonder in wonders" :key="wonder.id" class="wonder-card">
      <SingleWonder :wonders="wonder" />
    </div>
</div>

</template>
<script>
import SingleWonder from './SingleWonder.vue'

export default {
    name: 'WonderCard',
    props:{
        wonders: Array
    },
    components:{
        SingleWonder
    }
    
}
</script>

<style scoped>
.wonder-card-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 16px;
  padding: 20px;
}

.wonder-card {
  width: 300px;
  padding: 16px;
  border: 1px solid #ddd;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  background-color: #fff;
  transition: transform 0.2s, box-shadow 0.2s;
}

.wonder-card:hover {
  transform: scale(1.05);
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}
</style>