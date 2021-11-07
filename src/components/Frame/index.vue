<template>
  <div class="iframe-container">
    <iframe :src="src" frameborder="0"></iframe>
  </div>
</template>

<script>
export default {
  props: {
    src: {
      type: String,
    },
  },
};
</script>

<style lang="less" scoped>
.iframe-container {
  width: 100%;
  height: 100%;
  iframe {
    width: 100%;
    height: 100%;
    padding: 20px;
  }
}
</style>
