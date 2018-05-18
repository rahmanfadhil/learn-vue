<template>
  <div>
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    {{ name }}
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  data: () => ({
    name: 'Hello'
  }),
  components: {
    HelloWorld
  }
}
</script>
