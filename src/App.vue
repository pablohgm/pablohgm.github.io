<template>
  <div id="app">
    <outline></outline>
    <wordy></wordy>
  </div>
</template>

<script>
import Outline from './components/Outline';
import Wordy from './components/Wordy';

export default {
  name: 'app',
  components: {
    Outline,
    Wordy,
  },
};
</script>

<style lang="scss">
  @import 'assets/css/main';

  body {
    margin: 0px;
  }

  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: $color-font;
  }
</style>
