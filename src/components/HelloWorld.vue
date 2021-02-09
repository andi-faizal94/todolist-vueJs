<template>
  <div>
    <h2>TodoList</h2>
    <p v-if="items.length === 0">no items</p>
    <p v-for="item in items" :key="item.nama">
      {{item}}
      <button @click="remove(item)">hapus</button>
    </p>

    <p>{{item}}</p>
    <input type="text" v-model="item" />
    <input type="button" value="add" @click="add" />
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data: () => {
    return {
      items: ["nama", "kelas", "no"],
      item: ""
    };
  },
  methods: {
    add() {
      this.items.push(this.item);
      this.item = "";
    },
    remove(item) {
      const index = this.items.indexOf(item);
      this.items.splice(index, 1);
    }
  }
};
</script>


<style scoped>
</style>
