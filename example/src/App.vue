<template>
  <div id="app">
    <div class="container">
      <div v-for="timestamp in timestamps" class="item" :key="timestamp">
        <div class="ticker-wrapper">
          <span>Seconds</span>
          <vue-time-ticker class="ticker" :value="timestamp" format="SECONDS" />
        </div>
        <div class="ticker-wrapper">
          <span>Minutes</span>
          <vue-time-ticker class="ticker" :value="timestamp" format="MINUTES" />
        </div>
        <div class="ticker-wrapper">
          <span>Hours</span>
          <vue-time-ticker class="ticker" :value="timestamp" format="HOURS" />
        </div>
      </div>
    </div>
    <div class="controls">
      <div class="add-button" v-on:click="this.addTicker">
        Add new timestamp
      </div>
    </div>
  </div>
</template>

<script>
import VueTimeTicker from "vue-time-ticker";

export default {
  name: "App",
  components: {
    VueTimeTicker,
  },
  data: () => ({
    timestamps: [],
  }),
  methods: {
    addTicker() {
      const timestamp = prompt("Input timestamp:", new Date().toISOString());
      this.timestamps.push(timestamp);
    },
  },
};
</script>

<style scoped>
#app {
  max-height: 500px;
  height: 500px;
  width: calc(100% - 10px);
  background-color: lightslategray;
  border: 5px solid black;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.container {
  display: flex;
  align-items: flex-start;
  flex-direction: row;
  flex-basis: 300px;
  flex-wrap: wrap;
}

.item {
  flex-basis: 300px;
  flex-wrap: wrap;
  border: 1px solid black;
  border-radius: 3px;
  margin: 5px;
}

.ticker {
  font-weight: bolder;
}

.add-button {
  font-size: 20px;
  font-weight: bold;
  text-align: center;
  vertical-align: middle;
  margin: 5px;
  border-radius: 3px;
  border: 3px solid black;
  width: 200px;
}

.ticker-wrapper {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  font-size: 20px;
  font-weight: 500;
}
</style>
