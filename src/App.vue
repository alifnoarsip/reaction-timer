<template>
  <h1>Ninja Reaction Timer</h1>
  <div class="container">
    <button class="button" v-on:click="handlePlayClick">
      <span class="title">play</span>
    </button>
  </div>
  <div class="result" v-show="resulted">
    <p>Reaction time - {{ time }} ms</p>
    <h1 class="score">{{ titles[title_idx] }}</h1>
  </div>
  <div class="target" v-show="targetShow">
    <button class="largeButton" v-on:click="handleCatch">
      <h1>Catch me !!</h1>
    </button>
  </div>
  <!-- <Block />
  <Result /> -->
</template>

<script>
// import Block from "./components/Block";
// import Result from "./components/Result";

export default {
  name: "App",
  data() {
    return {
      title_idx: 0,
      titles: ["CUPU YEY", "MAYAN SIH..", "SUWANGARR"],
      startTime: 0,
      time: 0,
      resulted: false,
      targetShow: false,
    };
  },
  components: {
    // Block,
    // Result,
  },
  methods: {
    handlePlayClick() {
      this.targetShow = false;
      this.resulted = false;
      setTimeout(() => {
        this.targetShow = true;
        this.startTime = new Date().getTime();
      }, Math.random() * 3000 + 1000);
    },
    handleCatch() {
      this.targetShow = false;
      this.resulted = true;
      var now = new Date().getTime();
      this.time = now - this.startTime;

      if (this.time < 300) {
        this.title_idx = 2;
      } else if (this.time < 500) {
        this.title_idx = 1;
      } else {
        this.title_idx = 0;
      }
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.container {
  display: flex;
  justify-content: center;
  height: 100%;
  width: 100%;
}
.button {
  display: flex;
  background-color: green;
  width: 100px;
  height: 30px;
  justify-content: center;
  align-items: center;
  border-radius: 5px;
}
.title {
  color: white;
}

.largeButton {
  margin-top: 50px;
  background-color: yellowgreen;
  border-radius: 10px;
}
</style>
