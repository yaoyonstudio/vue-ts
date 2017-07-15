<template>
  <div class="test">
    <p>{{ propMessage }}</p>
    <p>{{ helloMsg }}</p>
    <button @click="greet()">Test Button</button>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Component from 'vue-class-component'

@Component({
  props: {
    propMessage: String
  }
})

export default class Test extends Vue {
  propMessage: string
  // inital data
  msg: number = 123
  // use prop values for initial data
  helloMsg: string = 'Hello, ' + this.propMessage
  // lifecycle hook
  mounted () {
    console.log('test component mounted')
  }
  // method
  greet () {
    alert('greeting: ' + this.msg)
  }
}
</script>

<style scoped lang="scss">
.test {
  width: 320px;
  margin: 20px auto;
  border: 1px solid #ddd;
  padding: 20px;
}
</style>
