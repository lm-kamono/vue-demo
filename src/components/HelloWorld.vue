<template>
  <div class="hello">
    <h1>{{ message }} - {{ time }}</h1>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    message: String,
    time: Number
  },
  data () {
    return {
      messageState: this.message
    }
  },
  created () {
    console.log('child - created')
    console.log('messageState', this.messageState)
  },
  mounted () {
    console.log('child - mounted')
  },
  beforeUpdate() {
    console.log('child - beforeUpdate')
  },
  updated() {
    console.log('child - updated')
  },
  beforeDestroy () {
    console.log('child - beforeDestroy')
  },
  destroyed () {
    console.log('child - destroyed')
  }
};
</script>
