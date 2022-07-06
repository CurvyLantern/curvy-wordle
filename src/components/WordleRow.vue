<script setup>
import LetterBox from './LetterBox.vue'

const props = defineProps({
  guessWord: Array
})
</script>

<template>
  <div class="row" >
    <LetterBox v-for="letter of guessWord" :letter="letter"/>
  </div>
</template>

<style scoped>
.row{
  display: flex;
  gap: 1rem;
}
</style>
