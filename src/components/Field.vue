<template>
  <div class="field">
    <div id="1" class="tile"></div>
    <div id="2" class="tile"></div>
    <div id="3" class="tile"></div>
    <div id="4" class="tile"></div>
    <div id="5" class="tile"></div>
    <div id="6" class="tile"></div>
    <div id="7" class="tile"></div>
    <div id="8" class="tile"></div>
    <div id="9" class="tile"></div>
  </div>
</template>

<script>
export default {
  name: 'Field',
}
</script>

<style>
.field {
  display: flex;
  flex-wrap: wrap;
  margin: 0 auto;
  width: 330px;
  gap: 10px;
}
.tile {
  width: 100px;
  height: 100px;
  border: 1px solid black;
}
</style>