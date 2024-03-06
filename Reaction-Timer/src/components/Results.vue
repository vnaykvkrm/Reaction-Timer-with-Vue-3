<script>
import lightningMcqueenImage from "@/assets/lightning-mcqueen.jpg";
import fastAndFuriousImage from "@/assets/fast-and-furious.jpg";
import runForestRunImage from "@/assets/run-forest-run.jpg";
import slothKingImage from "@/assets/sloth_king.jpg";

export default {
  props: ["score"],
  methods: {
    playerStatus() {
      if (this.score <= 100) {
        return "Lightning McQueen";
      } else if (this.score <= 200) {
        return "Fast and Furious";
      } else if (this.score <= 300) {
        return "Run Forest Run";
      } else {
        return "King of Sloth";
      }
    },
  },
  computed: {
    playerStatusImage() {
      if (this.score <= 200) {
        return lightningMcqueenImage;
      } else if (this.score <= 300) {
        return fastAndFuriousImage;
      } else if (this.score <= 400) {
        return runForestRunImage;
      } else {
        return slothKingImage;
      }
    },
  },
};
</script>
<template>
  <div class="results">
    <p class="reactionTime">Reaction time: {{ score }} ms</p>
    <p class="playerStatus">Woohoo! You are... {{ playerStatus() }}</p>
    <img :src="playerStatusImage" alt="image" class="image" />
  </div>
</template>

<style>
.results {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.reactionTime {
  font-size: 18px;
  font-weight: 700;
  margin: 20px;
  color: #0faf87;
}
.playerStatus {
  font-size: 35px;
  font-family: "Lucida Sans", "Lucida Sans Regular", "Lucida Grande",
    "Lucida Sans Unicode", Geneva, Verdana, sans-serif;
  font-style: italic;
  font-weight: bold;
  color: #0faf87;
}
.image {
  width: 200px;
  height: 200px;
  margin-top: 30px;
}
</style>
