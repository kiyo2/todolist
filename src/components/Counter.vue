<template>
  <div>
    <div>{{ countMessage }}</div>
    <button @click="count++">クリック！</button>
    <button @click="count = 0">リセット！</button>
  </div>
</template>

<script>
export default {
  name: "counter",
  data() {
    return {
      count: 0
    };
  },
  //↑countという名前の変数を定義している（コンポーネント内で利用する変数の書き方
  computed: {
    //computedという機能で表示するメッセージを生成する（表示と変数(count)を関連ずける）
    countMessage() {
      return "回数: " + this.count;
    }
  }
};
</script>

<style></style>