<template>
  <div>
    <div>ItemList</div>
    <div v-for="item in items" :key="item.name">
      <!--下を繰り返す-->
      <div class="item" :class="{over500: item.price >= 500}">
        <div class="name">名前: {{ item.name }}</div>
        <div class="price">{{ item.price }} 円</div>
        <div v-if="item.price >= 10000">高額商品</div>
      </div>
    </div>
    <div>
      <label>
        名前
        <input type="text" v-model="newItemName" />
      </label>
      <label>
        価格
        <input type="number" v-model="newItemPrice" />
      </label>
      <button @click="addItem">add</button>
    </div>
  </div>
</template>

<script>
export default {
  //nameとdataとmethods
  name: "ItemList",
  data() {
    return {
      items: [
        { name: "たまご", price: 100 },
        { name: "りんご", price: 160 }
      ],
      newItemName: "", //最初何も入力されていない
      newItemPrice: 0 //最初０と表示しておく
    };
  },
  methods: {
    addItem() {
      this.items.push({ name: this.newItemName, price: this.newItemPrice });
    }
  }
};
</script>

<style>
.over500 {
  color: red;
}
</style>