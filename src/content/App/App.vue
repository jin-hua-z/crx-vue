<template>
  <div class="main-app">
    <el-container>
      <el-header><HeaderNav /></el-header>
      <el-main>
        <div class="jus">
          <div class="search-box"><SearchBar /></div>
        </div>
      </el-main>
    </el-container>
  </div>
</template>

<script>
import HeaderNav from "@/components/HeaderNav";
import SearchBar from "./views/SearchBar";
export default {
  name: "app",
  components: {
    HeaderNav,
    SearchBar,
  },
};
</script>

<style lang="less" scoped>
.search-box {
  width: 576px;
}
</style>
