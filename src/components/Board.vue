<script setup>
import WordleRow from './WordleRow.vue'

import {ref , reactive} from 'vue'
const props = defineProps({
  guesses: Array
})
</script>

<template>
<!-- $ $ $ $ $ -->
<!-- $ $ $ $ $ -->
<!-- ... 6 times -->
<div>
  <div class="board-container">
  <WordleRow v-for="guess of guesses" :guessWord="guess"/>
  </div>
</div>
</template>

<style scoped>
.board-container {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
</style>
