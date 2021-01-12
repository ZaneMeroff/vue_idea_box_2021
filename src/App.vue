<template>
  <div id="app">

    <div class="main-app-container">
      <h1>iDeA bOx 💭</h1>
      <Form @addIdea="createIdea"/>
      <IdeasContainer :ideas="ideas" @delete="deleteIdea"/>
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
        ideas: [
          { id: 1, title: "Birds", description: "Falcon, Hawk, Eagle" },
          { id: 2, title: "Dogs", description: "Poodle, Retriever, Pug" },
          { id: 3, title: "Whiskey", description: "Beam, Jack, Henry" },
        ],
      }
    },
    methods: {

      createIdea(idea) {
        this.ideas.push({
          id: this.ideas.length+1,
          title: idea.title,
          description: idea.description,
        })
      },

      deleteIdea(id) {
        this.ideas = this.ideas.filter(idea => idea.id !== id)
      },
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
