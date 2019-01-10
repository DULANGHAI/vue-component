<template>
  <div class="about">
    <br>
    <h1>This is test child</h1>
    <h1>{{ `parent data test is ${parentData.test}` }}</h1>
    <button @click="changeParentValue">change value</button>
  </div>
</template>

<script>
export default {
  inject: ["parentData"],
  mounted() {
    // 监听自定义事件
    this.$on("test-emit", text => {
      console.log("子组件触发啦：" + text);
    });
  },
  methods: {
    changeParentValue() {
      this.parentData.changeValue(123);
      this.$emit("test-emit", [1, 2, 3]);
    }
  }
};
</script>
