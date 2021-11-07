<template>
  <div class="main-app">
    <el-container>
      <el-header>
        <HeaderNav>
          <div class="jus">
            <div class="search-box"><SearchBar /></div>
          </div>
        </HeaderNav>
      </el-header>
      <el-main>
        <ManyLinks :linksList="workList" key="1" title="快速工作" />
        <ManyLinks :linksList="feList" key="2" title="前端" />
        <ManyLinks :linksList="studyList" key="3" title="技术" />
        <ManyLinks
          :linksList="toolsList"
          key="4"
          title="在线工具"
          whatType="open"
        />
      </el-main>
    </el-container>
  </div>
</template>

<script>
import HeaderNav from "@/components/HeaderNav";
import SearchBar from "./views/SearchBar";
import ManyLinks from "./views/ManyLinks";
import logo from "assets/images/logo.png";
import { feList, studyList, workList, toolsList } from "utils";
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
      toolsList,
    };
  },
  mounted() {
    console.log("1234567ytrertytrewertytrewqwerty");
  },
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
