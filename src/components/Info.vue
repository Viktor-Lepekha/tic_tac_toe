<template>
  <h2 class="info">
    You are playing with {{playersColor}} color! 
  </h2>
</template>

<script>
export default {
  name: 'Info',
  props: ['playersColor'],
}
</script>