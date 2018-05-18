<template>
  <div>
    <h1>Hello World</h1>
    {{ name }}
    <hr/>
    <h2>Todo App</h2>
    <input type="text" v-on:keypress.enter="addItem" v-model="addInput" placeholder="Add Item">
    <button v-on:click="addItem">Add Item</button>
    <br/>
    <input type="text" v-model="searchInput" placeholder="Search Item">
    <ol>
      <li v-for="(item, index) in showItem" v-bind:key="index">
        <button v-on:click="deleteItem(index)">X</button>
        {{ item }}
      </li>
    </ol>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data: () => ({
    name: 'Rahman Fadhil',
    addInput: '',
    searchInput: '',
    items: ['Hello', 'World', 'Again']
  }),
  methods: {
    addItem() {
      this.items.push(this.addInput)
    },
    deleteItem(index) {
      this.items.splice(index, 1)
    }
  },
  computed: {
    showItem() {
      return this.items.filter(item =>
        item.toLocaleLowerCase().includes(this.searchInput.toLocaleLowerCase())
      )
    }
  },
  props: {
    msg: String
  }
}
</script>
