<template>
    <div class="wordy">
        <div>{{ msg }}</div>
    </div>
</template>

<script>
    export default {
      name: 'wordy',
      data() {
        return {
          msg: 'Wordy',
        };
      },
    };
</script>

<style lang="scss" scoped>

  .wordy {
    padding-left: 2%;
  }

</style>
