<template>
  <div class="about">
    <h1>
      This is an about page
    </h1>
    <input type="text" v-model="test">

    <test-child @test-emit="handleEmitTest"></test-child>
  </div>
</template>

<script>
import TestChild from "@/components/TestChild";

export default {
  components: {
    TestChild
  },
  provide() {
    return {
      parentData: this
    };
  },
  data() {
    return {
      test: "value is tests"
    };
  },
  methods: {
    changeValue(value) {
      this.test = value;
    },
    handleEmitTest(payload) {
      console.log("父组件触发啦:" + payload);
    }
  }
};
</script>
