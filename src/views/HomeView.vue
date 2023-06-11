<script>
import ClickEvent from "../components/ClickEvent.vue"

export default {
  components: { ClickEvent },
  data() {
    return {
      starting: false,
      start2: false,
      CounterAdd: 10,
      reactionTime: 0,
      maintime: null,
      secondtime: 0,
      finalSpeed: ["..Snails Pace", "..Ninja Speed", "..Snap Speed"]
    }
  },
  methods: {
    changeitsvalue() {
      let mainTime = Math.floor(Math.random() * 5 + 1) * 1000;
      this.reactionTime = 0;
      this.starting = true;
      setTimeout(() => {
        this.start2 = true;
        this.maintime = setInterval(() => {
          this.secondtime += this.CounterAdd;
        }, this.CounterAdd);
      }, mainTime);
    },
    calulatethetime() {
      this.start2 = false;
      this.starting = false;
      clearInterval(this.maintime);
      this.reactionTime = this.secondtime
      this.secondtime = 0
    }
  },
  computed: {
    resultSpeed() {
      if (this.reactionTime <= 250) {
        return this.finalSpeed[2]
      }
      else if (this.reactionTime <= 400 && this.reactionTime > 250) {
        return this.finalSpeed[1]
      } else {
        return this.finalSpeed[0]
      }
    }

  }
}
</script>

<template>
  <h1>Ninja Reaction Timer</h1>
  <div class="mainapp">
    <button :class="{ active: starting == true }" @click="changeitsvalue">Play</button>
    <ClickEvent :start2="start2" @closeit="calulatethetime" />
    <div class="text" v-if="reactionTime">
      <p>Reaction Time - {{ reactionTime }} ms</p>
      <h3>{{ resultSpeed }}</h3>
    </div>
  </div>
</template>

<style scoped>
* {
  font-family: sans-serif;
}

h1 {
  font-size: 25px;
  color: #443824;
  text-align: center;
}

.mainapp {
  text-align: center;
}

.mainapp>button {
  padding: 10px 15px;
  background-color: rgb(0, 196, 33);
  color: white;
  border: none;
  font-size: 18px;
  cursor: pointer;
  border-radius: 5px;
}

.mainapp>button.active {
  opacity: 0.5;
  user-select: none;
}

.mainapp .text h3 {
  font-size: 22px;
  color: rgb(0, 196, 33);
}</style>
