<template>
  <div id="app">

    <div class="main-app-container">
      <h1>iDeA bOx 💭</h1>

      <Form />
      <IdeasContainer />

    </div>

  </div>
</template>

<script>
  import Form from './components/Form.vue'
  import IdeasContainer from './components/IdeasContainer.vue'

  export default {
    name: "App",
    components: {
      Form,
      IdeasContainer,
    },
    data() {
      return {
        ideas: [],
      }
    },
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
    display: flex;
    flex-direction: column;
    align-items: center;
  }

</style>
