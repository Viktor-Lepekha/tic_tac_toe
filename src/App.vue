<template>
  <Header msg="Play tic tac toe against browser" />
  <div v-if="!playersColor">
    <ColorPicker :selectColor="pickColor"/>
  </div>
  <div v-if="playersColor">
    <Info :playersColor="this.playersColor" />
    <Field :playersColor="this.playersColor" :botColor="this.botColor" />
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
      playersColor: '',
      botColor: '',
    }
  },

  methods: {
    pickColor: function(color) {
      this.playersColor = color;
      if (this.playersColor === 'red') {
        this.botColor = 'yellow';
      } else {
        this.botColor = 'red';
      }
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
