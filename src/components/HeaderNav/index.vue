<template>
  <div class="custom-header-nav align-items jus font-20 w-600">
    <slot></slot>
  </div>
</template>

<script>
export default {
  props: {
    msg: String,
  },
};
</script>

<style lang="less" scoped>
.custom-header-nav {
  width: 100%;
  height: 100%;
}
</style>
