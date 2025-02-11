<template>
  <div v-html="tag"></div>
  <div>{{ tag }}</div>
  <form action="">
    <p>Two way binding</p>
    <input type="text" v-model="name" placeholder="Please enter your good name">
    <button type="submit" class="btn" @click="click()">Submit</button>
  </form>
</template> 

<script>
export default {
  name: 'DataBinding',
  data() {
      return {
        name: "",
        tag: "<h5>Data Binded</h5>"
      }
  },
  methods:{
    click() {
      alert("Hello"+ " " + this.name + "👋" + "\n" + "Have a Good Day!🎉");
    }
  }
}
</script>
<style lang="scss">
@import "../assets/scss/main.scss";
  h5 {
    color: $ivory;
  }
  form {
    @include rem-fallback(max-width, 400);
    margin: 0 auto;
    @include rem-fallback(margin-top, 30);
    p {
      color: $ivory;
    }
    input {
      display: block;
      width: 100%;
      @include rem-fallback(padding, 8, 12);
      @include rem-fallback(margin-bottom, 15);
      @include rem-fallback(font-size, 16);
      @include rem-fallback(border-radius, 5);
      outline: none;
      border: 2px solid transparent;
      transition: all 0.3s linear;
      &:focus {
        border-color: $teal;
      }
    }
  }
</style>