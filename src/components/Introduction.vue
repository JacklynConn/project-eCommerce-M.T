<template>
  <h1>I am {{ bio.name }}, I am an {{ bio.title }}</h1>
  <h1>I was born in {{ bio.dob }}</h1>
</template>

<script>
export default {
  props: ["bio"],
  setup(props, {emit}){
    emit("greeting", "I am child proerty, I'm from Introduction component");
  }
}
</script>

<style scoped>
h1{

}
</style>