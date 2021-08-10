<template>
  <div id="SweetTimer">05:00</div>
</template>

<script>
export default {
  name: 'SweetTimer',
  methods: {
    startTimer(duration, display) {
      let timer = duration,
        minutes, seconds;
      setInterval(function() {
        minutes = parseInt(timer / 60, 10)
        seconds = parseInt(timer % 60, 10);

        minutes = minutes < 10 ? "0" + minutes : minutes;
        seconds = seconds < 10 ? "0" + seconds : seconds;

        display.textContent = minutes + ":" + seconds;

        if (--timer < 0) {
          timer = duration;
        }
      }, 1000);
    }
  },
  mounted() {
      const oneMinutes = 60 * 1,
      display = document.querySelector('#SweetTimer');
      this.startTimer(oneMinutes, display);
  }
}
</script>

<style lang="sass">
#SweetTimer
  z-index: 1000000
</style>
