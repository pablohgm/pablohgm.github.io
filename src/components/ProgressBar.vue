<template>
    <div class="progress-bar">
        <div class="bar" :style="{width: value+'%'}"></div>
    </div>
</template>

<script>
    export default {
      name: 'progress-bar',
      props: ['percentage'],
      data() {
        return {
          value: this.percentage
        };
      }
    };
</script>

<style lang="scss" scoped>
  @import "../assets/css/main";

  .progress-bar {
    background-color: $color-secundary;
    margin-right: 6%;
    margin-bottom: 10px;
    margin-top: 10px;
  }

  .bar {
    background-color: $color-font-primary;
    height: 10px;
  }

</style>
