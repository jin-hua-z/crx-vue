<template>
  <div class="">
    <el-drawer
      size="90%"
      :visible.sync="drawer"
      :direction="direction"
      :before-close="handleClose"
      :destroy-on-close="true"
      :withHeader="false"
    >
      <Frame :src="src" v-if="src" />
      <span class="" v-else>数据异常</span>
    </el-drawer>
  </div>
</template>

<script>
import Frame from "components/Frame";
export default {
  components: { Frame },
  props: {
    drawer: {
      type: Boolean,
      default: false,
    },
    src: {
      type: String,
    },
  },
  data() {
    return {
      direction: "rtl",
    };
  },
  methods: {
    handleClose(done) {
      console.log("-------26", done);
      this.$emit("update:drawer", false);
    },
  },
};
</script>

<style></style>
