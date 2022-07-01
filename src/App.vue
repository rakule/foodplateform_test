<template>
  <div id="app">
    <HomeTest/>
  </div>
</template>

<script>


import HomeTest from './page/HomeTest.vue'

export default {
  name: 'App',
  components:{
    HomeTest,
}
}
</script>

<style>
@import url('./style/reset.css');
@import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;1,100;1,300;1,400;1,500;1,700&display=swap');
#app {
  font-family: 'Roboto', sans-serif;
  padding: 20px;
}
</style>
