<template>
  <div>
    <h1>Hello World</h1>
    {{ name }}
    <hr/>
    <h2>Todo App</h2>
    <input type="text" v-on:keypress.enter="addItem" v-model="addInput">
    <ul>
      <li v-for="(item, index) in items" v-bind:key="index">{{ item }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data: () => ({
    name: 'Rahman Fadhil',
    addInput: '',
    items: ['Hello', 'World', 'Again']
  }),
  methods: {
    addItem() {
      // console.log(this.addInput);
      this.items.push(this.addInput)
    }
  },
  props: {
    msg: String
  }
}
</script>
