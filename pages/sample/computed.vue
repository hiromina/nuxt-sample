<template>
  <section class="container">
    <h1>{{ title }}</h1>
    <label for="input">入力</label>
    <input type="text" id="input" v-model="inputItem" @keypress.enter="addItem">　<button @click="addItem">追加</button>
    <span v-if="inputItem">　大文字に変換: {{ upperCase }}</span>
    <span v-if="inputItem">　　文字数: {{ textSize }}</span>
    <br><br>
    <label for="search">検索</label>
    <input type="search" id="search" v-model="query">
    <ul>
      <li v-for="item in filteredItems">{{ item }}</li>
    </ul>
    <br>
    <hr>
    <n-link to="/sample">{{ from }}</n-link>
  </section>
</template>

<script>
export default {
  data() {
    return {
      title: 'Computed',
      from: 'Sample Page',
      inputItem: '',
      items: [],
      query: ''
    }
  },
  methods: {
    addItem() {
      this.items.push(this.inputItem);
      this.inputItem = '';
    }
  },
  computed: {
    upperCase() {
      return this.inputItem.toUpperCase();
    },
    textSize() {
      if(0 < this.inputItem.length) {
        return this.inputItem.length;
      }
    },
    filteredItems() {
      return this.items.filter((item) => item.includes(this.query));
    }
  }
}
</script>
