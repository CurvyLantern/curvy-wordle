<script setup>
const props = defineProps({
  letter : String
})
</script>

<template>
  <div class="letter-box" >{{letter}}</div>
</template>

<style scoped>
.letter-box {
  width: 50px;
  height:50px;
  display: flex;
  align-items: center;
  justify-content: center;
  border: 2px solid orangered;
  border-radius: 1rem;
}
</style>
