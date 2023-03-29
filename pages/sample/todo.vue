<template>
  <section class="container">
    <h1>{{ title }}</h1>
    <input v-model="newItem" @keypress.enter="addItem">
    <button @click="addItem">追加</button>
    <button @click="deleteItem">完了したものを削除</button>
    <br>
    <table v-for="item in items">
      <tr>
        <td :class="{ 'done' : item.isDone }"><input type="checkbox" v-model="item.isDone">{{ item.value }}</td>
      </tr>
    </table>
    <hr>
    <n-link to="/sample">{{ from }}</n-link>
  </section>
</template>

<script>
export default {
  data() {
    return {
      title: 'TODO List',
      from: 'Sample Page',
      newItem: '',
      items: []
    }
  },
  methods: {
    addItem() {
      if(!this.newItem) return;
      const item = {
        value: this.newItem,
        isDone: false
      }
      this.items.push(item);
      this.newItem = '';
    },
    deleteItem() {
      let newItems = [];
      for (let i = 0; i < this.items.length; i++) {
        if(!this.items[i].isDone) {
          newItems.push(this.items[i]);
        }
      }
      this.items = newItems;
    }
  }
}
</script>

<style scoped>
.done {
  text-decoration: line-through;
}
</style>
