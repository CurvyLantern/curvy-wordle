<script setup>
import Board from './components/Board.vue'
import {ref,reactive ,watch} from 'vue'

const guesses = reactive([
  ['','','','',''],
  ['','','','',''],
  ['','','','',''],
  ['','','','',''],
  ['','','','',''],
  ['','','','',''],
])
console.log(guesses)

const guess = ref('')
const index = ref(0)

watch(guess,cur=>{
  const arr = guesses[index.value]
  arr.forEach((val,i)=>{
    arr[i] = cur[i] || ''
  })
})

function onSubmit() {
  guess.value = ''
  index.value <= 5 && index.value++
}
</script>

<template>
<div>
  <Board :guesses="guesses"/>
  <div class="input-container">
    <input type="text" v-model="guess" @keydown.enter="onSubmit" size="5" maxlength="5">
    <button @click="onSubmit" type="button"> submit </button>
  </div>
</div>
</template>

<style scoped>
.input-container {
  margin-block: 2rem;
  display: flex;
}
input{
  padding-block: .5rem;
}
button{
  padding-inline: 2rem; 
}
</style>
