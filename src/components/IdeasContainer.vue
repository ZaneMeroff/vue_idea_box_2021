<template>
  <div class="ideas-outer-container">

    <Idea
      v-for="idea in ideas"
      :id="idea.id"
      :title="idea.title"
      :description="idea.description"
      @delete="handleDelete"
    />

    <p v-if="!ideas.length" class="no-idea-msg">you must not have any ideas at this time...</p>

  </div>
</template>

<script>
  import Idea from "./Idea.vue"
  export default {
    name: "IdeasContainer",
    components: {
      Idea,
    },
    props: {
      ideas: { type: Array, default: ()=> [] },
    },
    methods: {

      handleDelete(id) {
        this.$emit("delete", id)
      },
    },
  }
</script>

<style scoped>

  .ideas-outer-container {
    height: 100%;
    width: 100%;
    background-color: #ebeeee;
    display: flex;
    flex-wrap: wrap;
    overflow-y: scroll;
    
  }

  .no-idea-msg {
    margin: 100px 0px 0px 214px;
  }

</style>
