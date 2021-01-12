<template>
  <form class="form-outer-container">

    <input v-model="title" @change="validateInputs" class="form-item" placeholder="title"/>
    <input v-model="description" @change="validateInputs" class="form-item"placeholder="description"/>
    <button :disabled="saveDisabled" @click="handleSaveClick" class="form-item">save</button>

  </form>
</template>

<script>
  export default {
    name: "Form",
    props: [],
    data() {
      return {
        saveDisabled: true,
        title: "",
        description: "",
      }
    },
    methods: {

      validateInputs() {
        console.log("test");
        if (this.title && this.description) {
          this.saveDisabled = false
        } else {
          this.saveDisabled = true
        }
      },

      clearForm() {
        this.title = ""
        this.description = ""
      },

      handleSaveClick(e) {
        e.preventDefault()
        this.clearForm()
      },
    },
    mounted() {

    },
  }
</script>

<style scoped>

  .form-outer-container {
    border: 1px solid #000;
    height: auto;
    width: 100%;
    text-align: center;
  }

  .form-item {
    width: 200px;
    margin: 10px;
  }

</style>
