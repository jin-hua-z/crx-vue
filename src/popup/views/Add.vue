<template>
  <div>
    <el-form ref="form" :model="form" label-width="80px" size="small">
      <el-form-item label="名称1">
        <el-input type="input" v-model="form.name"></el-input>
      </el-form-item>
      <el-form-item
        v-for="(nav, index) in form.navList"
        :label="'导航' + index"
        :key="nav.key"
        :prop="'navList.' + index + '.value'"
      >
        <el-row>
          <el-col :span="12">
            <el-form-item label="名称">
              <el-input type="input" v-model="nav.name"></el-input>
            </el-form-item>
          </el-col>
          <el-col :span="12">
            <el-form-item label="图标">
              <el-input type="input" v-model="nav.icon"></el-input>
            </el-form-item>
          </el-col>
          <el-col :span="12">
            <el-form-item label="链接">
              <el-input type="input" v-model="nav.link"></el-input>
            </el-form-item>
          </el-col>
          <el-col :span="12">
            <el-row>
              <el-col :span="12">
                <el-form-item label="状态">
                  <el-switch v-model="nav.able"></el-switch>
                </el-form-item>
              </el-col>
              <el-col :span="12">
                <el-link
                  type="danger"
                  icon="el-icon-delete"
                  circle
                  @click.prevent="removeDomain(nav)"
                ></el-link>
              </el-col>
            </el-row>
          </el-col>
        </el-row>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="onSubmit">立即创建</el-button>
        <el-button @click="addDomain">新增域名</el-button>
        <el-button>取消</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  name: "Add",
  data() {
    return {
      form: {
        name: "",
        navList: [
          {
            value: "",
          },
        ],
      },
    };
  },
  methods: {
    onSubmit() {
      console.log("submit!");
    },
    removeDomain(item) {
      var index = this.dynamicValidateForm.domains.indexOf(item);
      if (index !== -1) {
        this.dynamicValidateForm.domains.splice(index, 1);
      }
    },
    addDomain() {
      this.dynamicValidateForm.domains.push({
        value: "",
        key: Date.now(),
      });
    },
  },
};
</script>

<style>
</style>