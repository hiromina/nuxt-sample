<template>
  <section class="container">
    <h1>{{ title }}</h1>
    <h2>リストの入力／検索</h2>
    <div class="blue">
      <p>
        入力：<input type="text" id="input" v-model="inputItem" @keypress.enter="addItem">
        <button @click="addItem">追加</button>
        <span v-if="inputItem">　大文字に変換: {{ upperCase }}</span>
        <span v-if="inputItem">　文字数: {{ textSize }}</span>
      </p>
      <p>
        検索：<input type="search" id="search" v-model="query">
        <ul>
          <li v-for="item in filteredItems">{{ item }}</li>
        </ul>
      </p>
      <button @click="clear">リストを削除</button>
    </div>
    <h2>フルネーム表示</h2>
    <div class="blue">
      <p>
        姓：<input type="text" v-model="lastName">
      </p>
      <p>
        名：<input type="text" v-model="firstName">
      </p>
      <p>
        フルネーム：{{ fullName }}
      </p>
    </div>
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
      query: '',
      lastName: '',
      firstName: ''
    }
  },
  methods: {
    addItem() {
      this.items.push(this.inputItem);
      this.inputItem = '';
    },
    clear() {
      this.items = [];
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
    },
    fullName() {
      return this.lastName + ' ' + this.firstName;
    }
  }
}
</script>

<style scoped>
.blue {
  background-color: aliceblue;
  width: 50%;
  padding: 10px;
  margin-bottom: 20px;
}
h2 {
  font-size: medium;
}
</style>
