<template>
  <div>
    <el-input
      placeholder="切换TAB，输入查询关键词"
      v-model="keyword"
      class="input-with-select"
      @keyup.enter.native="handleSearch"
    >
      <el-select v-model="select" slot="prepend" placeholder="请选择" @change="onChange">
        <el-option
          :label="item.label"
          :value="item.value"
          v-for="item in platformList"
          :key="item.value"
        ></el-option>
      </el-select>
    </el-input>
  </div>
</template>

<script>
import { platformList, addSub } from "utils";

export default {
  components: {},
  data() {
    return {
      keyword: "",
      select: "1",
      platformList: platformList || [],
      targetInfo: this.foramtFunc(this.targetInfo)[0] || {},
    };
  },
  mounted() {
    this.targetInfo = this.foramtFunc(this.platformList)[this.select] || {};
  },
  methods: {
    foramtFunc(arr = []) {
      const target = [];
      arr.forEach(item => {
        target[item.value] = {
          ...item,
        };
      });
      return target;
    },
    onChange(value) {
      this.targetInfo = this.foramtFunc(this.platformList)[value] || {};
    },
    handleSearch(e) {
      if (!e.target.value) {
        return;
      }
      const href = `${this.targetInfo.link}${this.keyword}`;
      href && window.open(addSub(href));
    },
  },
};
</script>

<style lang="less">
.el-select .el-input {
  width: 120px;
}
.input-with-select .el-input-group__prepend {
  background-color: #fff;
}
.el-input .el-input--suffix {
  .el-input__inner {
    font-size: 20px;
    font-weight: 600;
  }
}
</style>
