<template>
  <div class="idea-outer-container">

    <button @click="handleDelete" class="delete-btn">X</button>
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
    methods: {

      handleDelete() {
        this.$emit("delete", this.id)
      },
    },
  }
</script>

<style scoped>

  .idea-outer-container {
    background-color: #fff;
    box-shadow: 5px 10px 18px #bbbbbb;
    height: 150px;
    width: 150px;
    text-align: center;
    margin: 10px;
    border-radius: 5px;
  }

  .delete-btn {
    background-color: #ffc1c1;
    border: none;
    height: 20px;
    width: 20px;
    border-radius: 10px;
    padding-top: 2px;
    margin: 7px 0px 0px 115px;
  }

  .delete-btn:hover {
    cursor: pointer;
    background-color: #ff4b4b;
  }

</style>
