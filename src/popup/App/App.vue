<template>
  <div class="main-app pop-container">
    <div class="form-wrapper">
      <el-form ref="form" :model="form" label-width="80px" size="small">
        <el-form-item label="操作">
          <el-select v-model="form.operate" placeholder="请选择操作类型">
            <el-option label="新增导航" value="add"></el-option>
            <el-option label="编辑导航" value="edit"></el-option>
          </el-select>
        </el-form-item>

        <component :is="currentTabComponent" />
      </el-form>
    </div>
  </div>
</template>

<script>
import { Edit, Add } from "../views";
export default {
  components: { Edit, Add },
  data() {
    return {
      /** 默认新增 */
      currentTabComponent: "Add",
      form: {
        operate: "add",
      },
    };
  },
  methods: {
    onSubmit() {
      console.log("submit!");
    },
  },
};
</script>

<style lang='less' scoped>
.main-app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  width: 160px;
}
.pop-container {
  width: 800px;
  height: 720px;
  margin: auto;
  .form-wrapper {
    padding-top: 60px;
    width: 700px;
  }
  .el-select {
    width: 100%;
  }
}
</style>
