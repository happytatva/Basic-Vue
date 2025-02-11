<template>
  <div v-html="tag"></div>
  <div>{{ tag }}</div>
</template>

<script>
export default {
  name: 'DataBinding',
  data() {
      return {
          tag: "<h5>Data Binded</h5>"
      }
  }
}
</script>
<style lang="scss">
@import "../assets/scss/main.scss";
  h5 {
    color: $ivory;
  }
</style>