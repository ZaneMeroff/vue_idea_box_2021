<template>
  <form class="form-outer-container">

    <input v-model="title" type="text" class="form-item" placeholder="title"/>
    <input v-model="description" type="text" class="form-item"placeholder="description"/>
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
        this.$emit("addIdea", { title: this.title, description: this.description })
        this.clearForm()
      },
    },
    watch: {
      title() { this.validateInputs() },
      description() { this.validateInputs() },
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

  button:hover {
    cursor: pointer;
  }

</style>
