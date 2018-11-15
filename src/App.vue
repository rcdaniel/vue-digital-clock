<template>
  <div>
    <html-clock theme="red-lcd"></html-clock>
  </div>
</template>

<script>
import HTMLClock from './components/HTMLClock'
export default {
    components: {
      'html-clock': HTMLClock
    }
}
</script>


<style>
  :root {
    text-align: center;
  }

  h1 {
    font-family: Montserrat, Impact, sans-serif;
    font-size: 72px;
  }
</style>
