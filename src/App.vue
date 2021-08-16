<template>
  <Header msg="Play tic tac toe against browser"/>
  <Field />
</template>

<script>
import Header from './components/Header.vue'
import Field from './components/Field.vue'

export default {
  name: 'App',
  components: {
    Header,
    Field
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
