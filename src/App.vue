<template>
  <Header msg="Play tic tac toe against browser" />
  <div v-if="!color">
    <ColorPicker :selectColor="pickColor"/>
  </div>
  <div v-if="color">
    <Info :playersColor="this.color" />
    <Field :playersColor="this.color" />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import ColorPicker from './components/ColorPicker.vue'
import Info from './components/Info.vue'
import Field from './components/Field.vue'

export default {
  name: 'App',
  components: {
    Header,
    ColorPicker,
    Info,
    Field
  },
  data() {
    
    return {
      color: ''
    }
  },

  methods: {
    pickColor: function(color) {
      console.log('called')
      this.color = color;
    }
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
