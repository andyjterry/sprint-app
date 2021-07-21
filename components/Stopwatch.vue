<template>
  <div id="stopwatch">
    <button @click="start">Start</button>
    <button @click="stop">Stop</button>
    <button @click="reset">Reset</button>
    <p>{{formattedElapsedTime}}</p>
  </div>
</template>

<script>
export default {
  name: "stopwatch",
  data() {
    return {
      elapsedTime: 0,
      timer: undefined
    };
  },
  computed: {
    formattedElapsedTime() {
      const date = new Date(null);
      date. setUTCMilliseconds(this.elapsedTime / 1000;
      const utc = date.toUTCString();
      return utc.substr(utc.indexOf(":") - 3, 10);
    }
  },
  methods: {
    start() {
      this.timer = setInterval(() => {
        this.elapsedTime += 1000;
      }, 1000);
    },
    stop() {
      clearInterval(this.timer);
    },
    reset() {
      this.elapsedTime = 0;
    }
  }
};
</script>
<!--<style>-->
<!--@import url('https://fonts.googleapis.com/css?family=Share+Tech+Mono');-->

<!--html, body {-->
<!--  padding: 0; margin: 0;-->
<!--  width: 100%;-->
<!--  height: 100%;-->
<!--}-->
<!--body {-->
<!--  background-color: rgb(10, 10, 10);-->
<!--  font-family: 'Share Tech Mono', sans-serif;-->
<!--  display: flex;-->
<!--  flex-direction: row;-->
<!--  flex-wrap: nowrap;-->
<!--  justify-content: center;-->
<!--  align-content: stretch;-->
<!--  align-items: center;-->
<!--}-->
<!--#clock {-->
<!--  order: 0;-->
<!--  flex: 0 1 auto;-->
<!--  align-self: center;-->
<!--  color: white;-->
<!--}-->

<!--.time {-->
<!--  font-size: 6.5em;-->
<!--}-->

<!--.text {-->
<!--  margin-top: 30px;-->
<!--  font-size: 5px;-->
<!--  color: white;-->
<!--  text-align: center;-->
<!--}-->

<!--a {-->
<!--  text-decoration: none;-->
<!--  color: inherit;-->

<!--  transition: color .1s ease-out;-->
<!--}-->

<!--.btn-container {-->
<!--  display: flex;-->
<!--  margin-top: 15px;-->
<!--}-->

<!--a {-->
<!--  text-align: center;-->
<!--  font-family: 'Share Tech Mono', sans-serif;-->
<!--  background: transparent;-->
<!--  /*border: 3px solid white;*/]-->
<!--  border:none;-->
<!--  color: white;-->
<!--  padding: 10px 15px;-->
<!--  margin: 0 10px;-->
<!--  text-transform: uppercase;-->
<!--  font-size: 2em;-->
<!--  cursor: pointer;-->
<!--  flex-grow: 1;-->
<!--  transition: color .1s ease-out;-->
<!--}-->
<!--</style>-->
