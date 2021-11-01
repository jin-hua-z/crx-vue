<template>
  <div>
    <p class="flex-start font-18 w-500">{{ title }}</p>
    <div class="fast-item-group flex">
      <div
        class="fast-item flex"
        v-for="item in linksList"
        :key="item.id"
        @click="handleClick(item)"
      >
        <img :src="logo" alt="" class="item-pic" />
        <span class="item-content">{{ item.label }}</span>
      </div>
    </div>
  </div>
</template>

<script>
import logo from "assets/images/logo.png";
import { addSub } from "utils";

export default {
  props: {
    title: {
      type: String,
      default: "访问",
    },
    linksList: {
      type: Array,
      default: () => [],
    },
  },
  data() {
    return {
      logo,
    };
  },
  methods: {
    handleClick(item) {
      item.link && window.open(addSub(item.link));
    },
  },
};
</script>

<style lang="less" scoped>
.fast-item-group {
  flex-wrap: wrap;
  .fast-item {
    width: 100px;
    display: flex;
    flex-direction: column;
    box-shadow: 0 0 10px 0 rgba(0, 0, 0, 0.1);
    align-items: center;
    border-radius: 4px;
    margin-right: 20px;
    cursor: pointer;
    &:hover {
      transform: scale(1.2);
      transition: all 0.3s;
    }
    .item-pic {
      width: 72px;
      height: 72px;
      padding: 10px;
    }
    .item-content {
      padding-bottom: 10px;
    }
  }
}
</style>
