
<template>
  <div class="flex flex-col gap-4 items-center justify-center pt-8">
   <h1 class="text-3xl font-bold">Vue Reaction Timer</h1> 
   <button class="py-2 px-8 bg-green-500 text-white cursor-pointer m-2 rounded-md" @click="start" :disabled="isPlaying">play</button>
   <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
   <Results v-if="showScore" :score="score"/>
  </div>
</template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'
export default {
  name: 'App',
  components: { Block, Results },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showScore: false,
    }
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000 
      this.isPlaying = true
      this.showScore = false
    },
    endGame(reactionTime) {
      this.score = reactionTime
      this.isPlaying = false
      this.showScore = true
    }
  }
    
  }
</script>



