<template>
    <div class="html-clock">
        <div :class="{
            hours: true,
            theme: theme
            }">{{ hours }}</div>
        <div class="sep">:</div>
        <div class="minutes">{{ minutes }}</div>
        <div class="sep">:</div>
        <div class="seconds">{{ seconds }}</div>
        <div class="mode">:</div>
    </div>
</template>

<style lang="postcss" scoped>
.html-clock {
  display: grid;
  grid-template-columns: 3fr 1fr 3fr 1fr 3fr 1.5fr;
  justify-content: center;
  align-content: center;
  width: 500px;
  height: 125px;
}

.html-clock > div {
  display: flex;
  justify-content: center;
}

.sep { animation: blink 1s linear infinite; }

@keyframes blink {
  0%,
  49% { opacity: 1; }

  50%,
  100% { opacity: 0; }
}

.red-lcd { color: red; }
.green-lcd { color: green; }
.blue-lcd { color: blue; }
</style>


<script>
var moment = require('moment');

export default {
    props: ['theme'],
    data: function () {
        return {
            hours: "--",
            minutes: "--",
            seconds: "--"
    }},
    methods: {
        updateTime() {
            this.seconds = moment().format("ss");
            this.minutes = moment().format("mm");
            this.hours = moment().format("H");
        }
    },
    mounted () {
        setInterval(this.updateTime, 1000);
    },
    watch: {}
}
</script>

