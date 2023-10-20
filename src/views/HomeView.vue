<script>
// importing child components
import HelloWorld from '../components/HelloWorld.vue'
export default {
  // registering child components
  components: {
    HelloWorld
  },
  data() {
    return {
      msg: "Weather API Retrieval Application" // testing sending props and data through views/comps
    }
  }
}
</script>

<template>
  <main>
    <div class="wrapper">   
      <HelloWorld :msg="msg"/>
    </div>
  </main>
</template>


<style>
  /* Bootstrap styling */
  @import "../assets/base.css";
</style>
