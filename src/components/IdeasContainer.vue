<template>
  <div class="ideas-outer-container">

    <Idea
      v-for="idea in ideas"
      :id="idea.id"
      :title="idea.title"
      :description="idea.description"
      @delete="handleDelete"
    />

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
    data() {
      return {

      }
    },
    methods: {

      handleDelete(id) {
        this.$emit("delete", id)
      },
    },
    mounted() {

    },
  }
</script>

<style scoped>

  .ideas-outer-container {
    height: 100%;
    width: 100%;
    text-align: center;
  }

</style>
