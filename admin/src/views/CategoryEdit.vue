<template>
  <div class="category-edit">
    <h1>新建分类</h1>
    <el-form label-width="80px" @submit.native.prevent="save">
      <el-form-item label="名称">
        <el-input placeholder="请输入名称" v-model="model.name"></el-input>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" native-type="submit">保存</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>
<script>
export default {
  data () {
    return {
      model: {
        name: ''
      }
    }
  },
  methods: {
    async save() {
      await this.$http.post('categories', this.model)
      this.$router.push('/categories/list')
      this.$message({
        type: 'success',
        msg: '新建成功'
      })
    }
  }
}
</script>
<style scoped>
</style>
