<template>
  <div class="container">
    <!-- <HelloWorld :msg="details.message" :training="details.training" :trainersName="details.trainers" :details="details"/> -->
    <HelloWorld :details="details"/>
    <DataBinding />
  </div>
</template>
<script>
import DataBinding from '@/components/data-binding.vue';
import HelloWorld from '../components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld, DataBinding
  },
  data(){
    return{
      details: {
        message: "Training Demo",
        training: "Vue",
        trainers: "Divyani, Bhautik"
      }
    }
  }
}
</script>