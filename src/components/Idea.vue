<template>
  <div class="idea-outer-container">

    <button @click="handleDelete">X</button>
    <p>{{ id }}</p>
    <p>{{ title }}</p>
    <p>{{ description }}</p>

  </div>
</template>

<script>
  export default {
    name: "IdeasContainer",
    props: {
      id:           { type: Number, default: 0 },
      title:        { type: String, default: "" },
      description:  { type: String, default: "" },
    },
    data() {
      return {

      }
    },
    methods: {

      handleDelete() {
        this.$emit("delete", this.id)
      },
    },
    mounted() {

    },
  }
</script>

<style scoped>

  .idea-outer-container {
    border: 2px solid #000;
    height: 150px;
    width: 150px;
    text-align: center;
  }

</style>
