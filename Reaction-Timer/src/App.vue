<template>
  <h1>Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">Play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame" />
  <Results v-if="showResults" :score="score" />
</template>
<script>
import Block from "./components/Block.vue";
import Results from "./components/Results.vue";
export default {
  name: "app",
  components: { Block, Results },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: 0,
      showResults: false,
    };
  },
  methods: {
    start() {
      this.isPlaying = true;
      this.delay = 2000 + Math.random() * 5000;
      this.showResults = false;
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = false;
      this.showResults = true;
    },
  },
};
</script>

<style>
#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 50px;
}
button {
  background: #000000;
  margin-top: 30px;
  color: white;
  border: none;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 16px;
  letter-spacing: 1px;
  cursor: pointer;
}
button:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}
h1 {
  font-size: 50px;
  font-weight: 700;
  margin: 10px;
}
</style>
