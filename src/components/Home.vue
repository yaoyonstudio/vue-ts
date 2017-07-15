<template>
  <div class="home">
    <h1>{{ title }}</h1>
    <p>{{ computedMsg }}</p>
    <test prop-message="test prop message"></test>
    </ul>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Component from 'vue-class-component'
import Test from './Test'

@Component({
  components: {
    Test
  }
})

export default class Home extends Vue {
  propMessage: string
  // inital data
  title: string = 'Vue 2.3+ with Typescript'
  // lifecycle hook
  created () {
    console.log('Home page created')
  }
  mounted () {
    console.log(this)
    console.log('Home page mounted')
  }
  // computed
  get computedMsg () {
    return 'computed: ' + this.title
  }
}
</script>

<style scoped lang="scss">
.home {
  p {
    color: #dd3333;
  }
}
</style>
