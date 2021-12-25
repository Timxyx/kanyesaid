<template>
  <div class="main">
    <p class="header">GET YOUR DAILY DOSE OF KAYNE QUOTES</p>
    <div class="home">
      <Zitat/>
    </div>
  </div>
</template>

<script>

import Zitat from '../components/Zitat.vue'

export default {
  name: 'Home',
  components: {Zitat}
}
</script>

<style>
  .home{
    display: flex;
    justify-content: center;
    
  }
  .main{
    font-family: Trebuchet MS;
    flex-direction: column;
    margin: 0;
    padding: 0;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #468C98;
  }
  .header{
    margin: 30px;
    margin-top: 20px;
    font-style: bold;
    font-size: 30px;
  }
</style>