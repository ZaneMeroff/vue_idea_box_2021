<template>
  <div id="app">

    <div class="main-app-container">
      <h1>iDeA bOx 💭</h1>
    </div>

  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>

  #app {
    width: 100%;
    height: auto;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .main-app-container {
    margin: 0px;
    border: 1px solid #000;
    height: 500px;
    width: 700px;
    text-align: center;
  }

</style>
