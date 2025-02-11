<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <!-- <p>Training: {{ training }}</p>
    <p>Trainers: {{ trainersName }}</p> -->
    <h1>{{ details.message }}</h1>
    <p>Training: {{ details.training }}</p>
    <p>Trainers: {{ details.trainers }}</p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
    // training: String,
    // trainersName: String,
    details: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../assets/scss/main.scss";
h1 {
  color: $teal;
  @include rem-fallback(margin-bottom, 15);
}
</style>
