<template>
  <div class="main-app">
    <el-container>
      <el-header><HeaderNav /></el-header>
      <el-main>
        <div class="jus">
          <div class="search-box"><SearchBar /></div>
        </div>
        <ManyLinks :linksList="workList" key="1" />
        <ManyLinks :linksList="feList" key="2" />
        <ManyLinks :linksList="studyList" key="3" />
      </el-main>
    </el-container>
  </div>
</template>

<script>
import HeaderNav from "@/components/HeaderNav";
import SearchBar from "./views/SearchBar";
import ManyLinks from "./views/ManyLinks";
import logo from "assets/images/logo.png";
import { feList, studyList, workList } from "utils";
export default {
  name: "app",
  components: {
    HeaderNav,
    SearchBar,
    ManyLinks,
  },
  data() {
    return {
      imgsArr: [
        {
          src: logo,
        },
      ],
      feList: feList,
      studyList: studyList,
      workList,
    };
  },
  mounted() {},
};
</script>

<style lang="less" scoped>
.search-box {
  width: 576px;
}
.item1 {
  width: 100px;
  height: 100px;
}
.item2 {
  width: 130px;
  height: 140px;
}
.img-info {
  width: 160px;
  height: 180px;
}
</style>
