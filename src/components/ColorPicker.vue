<template>
  <div class="colorPicker">
    <div>Choose your color:</div> 
    <div
      id="red"
      class="option option-red"
      v-on:click="selectColor('red')"
    ></div>
    <div
      id="yellow"
      class="option option-yellow"
      v-on:click="selectColor('yellow')"
    ></div>
  </div>
</template>

<script>
export default {
  name: 'ColorPicker',
  props: ['playersColor', 'selectColor'],
}
</script>

<style>
.colorPicker {
  width: 250px;
  height: 30px;
  line-height: 30px;
  margin: 0 auto;
  display: flex;
  justify-content: space-around;
  align-content: center;
}
.option {
  display: inline-block;
  width: 30px;
  height: 30px;
  border: 1px solid black;
  border-radius: 50%;
}

.option:hover {
  cursor: pointer;
}

.option-red {
  background-color: red;
}

.option-yellow {
  background-color: yellow;
}
</style>