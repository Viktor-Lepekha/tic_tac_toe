<template>
  <div class="info">
    You are playing with {{playersColor}} color! 
  </div>
</template>

<script>
export default {
  name: 'Info',
  props: ['playersColor'],
}
</script>