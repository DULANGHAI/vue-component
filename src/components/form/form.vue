<template>
  <form>
    <slot></slot>
  </form>
</template>

<script>
export default {
  name: "ElForm",
  props: {
    model: {
      type: Object
    },
    rules: {
      type: Object
    }
  }
};
</script>
