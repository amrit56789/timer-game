<template>
<div class="result">
    <template v-if="!isStart">
        <div class="score" v-if="earlyTime">
            <h2 v-if="score > 0">Your score is {{ score }}</h2>
            <h2 v-else>Too quick... Try again!</h2>
        </div>
        <h2 class="score" v-else>Click Go to test your reaction time!</h2>
    </template>
    <template v-else-if="isStart">
        <h2 class="score">Pay attention. Click Stop when the color changes</h2>
    </template>
    <div class="highScore" v-if="parseFloat(highScore) > 0">
        <h3>Your best reaction time was {{ highScore }} seconds</h3>
    </div>
</div>
</template>

<script>
export default {
    name: "GameResult",
    data() {
        return {
            localScore: 0,
            localHighScore: 0,
        };
    },
    props: ["score", "highScore", "isStart", "earlyTime"],
    computed: {
        highScoreProp() {
            return this.highScore;
        }
    },
    methods: {},
};
</script>
  
  
<style scoped>
.result {
    width: 500px;
    height: 140px;
    border: none;
    border-radius: 20px;
    background-color: #D9EDF7;
    color: black;
    font-family: Arial, Helvetica, sans-serif;
    font-size: 15px;
}

.score {
    margin-left: 20px;
    margin-top: 15px;
}

.highScore {
    margin-top: 40px;
    margin-left: 20px;
}
</style>
