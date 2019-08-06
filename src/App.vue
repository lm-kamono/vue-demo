<template>
  <div id="app">
    <HelloWorld :message="message" :time="time" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "app",
  components: {
    HelloWorld
  },
  data () {
    return {
      time: Date.now(),
      timerId: null
    }
  },
  computed: {
    message () {
      console.log('computed')
      return 'Hello World!'
    }
  },
  created () {
    console.log('created')
    this.timerId = setInterval(() => {
      this.time = Date.now()
    }, 1500)
  },
  mounted () {
    console.log('mounted')
  },
  beforeUpdate() {
    console.log('beforeUpdate')
  },
  updated() {
    console.log('updated')
  },
  beforeDestroy () {
    console.log('beforeDestroy')
  },
  destroyed () {
    console.log('destroyed')
    clearInterval(this.timerId)
  }
};
</script>
