<template>
  <el-input v-model="input" class="searchbox" placeholder="请输入内容" :value="keyword" prefix-icon="el-icon-search"></el-input>
</template>
<script>
export default {
  name: "SearchBox",
  props: {
    keyword: String,
  },
};
</script>
<style scoped>
.searchbox{
    width: 733px;
    margin: 30px;
}
</style>