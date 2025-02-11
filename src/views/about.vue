<template>
  <div class="container">
    <div class="custom-box">
      <h2>Interpolation with data</h2>
      <br>
      <p>My Name: {{ name }}</p>
      <p>Working In {{ company }}</p>
      <P>Work Experience: {{ 6 + 6 }} months</P>
      <!-- <p>whole function: {{ getContact() }}</p> -->
      <p>Contact Me: {{ getContact().email }} / {{ getContact().phone }}</p>
    </div>
    <div class="custom-box">
      <h2>Vue Methods</h2>
      <h4>Employee Details</h4>
      <p>Name: {{ getDetails().name }}</p>
      <p>Email: {{ getDetails().email }}</p>
      <p>Phone: {{ getDetails().phone }}</p>
      <h4>Get Employee Details Dynamically</h4>
      <p>Name: {{ getDetailsDynamic("Yash","","").name }}</p>
      <p>Email: {{ getDetailsDynamic("","xyz@gmail.com","").email }}</p>
      <p>Phone: {{ getDetailsDynamic("","","9899856560").phone }}</p>
    </div>
    <div class="custom-box">
      <h2>Vue Events</h2>
      <div class="btn-wrap">
        <button class="btn" v-on:click="click()">Click Me</button>
        <button class="btn secondary-btn" @mouseenter="mouseenter()" @mouseleave="mouseleave()">Hover Me</button>
        <button class="btn" @click="increase()">Count Me</button>
      </div>
      <p>Note: While hover pls see console</p>
      <p>Your count: <span class="highlighted">{{ count }}</span></p>
    </div>
  </div>
</template>
<script>
  export default {
    name: 'About',
    data() {
      return{
        count: 0,
        name: "Happy",
        company: "Tatvasoft",
        getContact: function(){
          return {
            email: "abc@gmail.com",
            phone: "9876543210"
          }
        }
      }
    },
    methods: {
      increase(){
        this.count++;
      },
      click(){
        alert("Wohoo!! You clicked me🎉");
      },
      mouseenter(){
        console.log ("enter")
      },
      mouseleave(){
        console.log ("leaving...")
      },
      getDetails(){
        return {
          name: this.name,
          email: this.getContact().email,
          phone: this.getContact().phone,
        }
      },
      getDetailsDynamic(name,email,phone){
        return {
          name: name,
          email: email,
          phone: phone,
        }
      }
    }
  }
</script>
<style scoped lang="scss">
  @import "@/assets/scss/main.scss";
  .highlighted {
    color: $teal2;
  }
  h4 {
    @include rem-fallback(margin, 5, 0, 15);
    color: $primary-color;
  }
  .btn-wrap {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    @include rem-fallback(margin, 8, 0);
    @include rem-fallback(gap, 15);
  }
</style>