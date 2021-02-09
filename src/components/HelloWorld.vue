<template>
  <div>
    <h2>Todolist</h2>
    <!-- menampilkan no items ketika item dihapus semua -->
    <p v-if="items.length === 0">No Items</p>
    <!-- akhir menampilka item -->
    <!-- mengambil data/state  -->
    <p v-for="item in items" :key="item.nama">
      {{item}}
      <!-- akhir mengambil data/state -->

      <!-- button removeItem dengan mengambil fungsi removeItem -->
      <button @click="removeItem(item)">hapus</button>
    </p>
    <p>{{item}}</p>
    <input type="text" v-model="item" />
    <!-- button addItems dengan mengambil fungsi addItems -->
    <input type="button" value="add" @click="addItems" />
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data: () => {
    return {
      items: ["nama", "kelas"],
      item: ""
    };
  },
  methods: {
    addItems() {
      this.items.push(this.item);
      this.item = "";
    },
    removeItem(item) {
      const index = this.items.indexOf(item);
      this.items.splice(index, 1);
    }
  }
};
</script>


<style scoped>
</style>
