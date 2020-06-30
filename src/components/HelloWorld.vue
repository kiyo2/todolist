<template>
  <div>
    <h1>{{ msg }}</h1>
    <!--Vueのコンポーネントは一つのタグの中におさまっている必要がある。多くの場合divタグで囲まれている-->
    <counter />
    <item-list />
    <!--構造として形式的に書く-->
  </div>
</template>

<script>
import Counter from "./Counter.vue";
//Counterコンポーネントを読み込む
import ItemList from "./ItemList.vue";
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  components: {
    Counter,
    ItemList
  }
  //templateタグ内でCounter(ItemList)コンポーネントを使えるようにする
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
