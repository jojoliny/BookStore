<template>
  <div style="margin:auto;width:733px">
    <el-card class="box-card product" shadow="never">
      <template #header>
        <div class="card-header">
          <h5 class="title">{{ title }}</h5>
        </div>
      </template>
      <ul class="product-info">
        <li>
          <span>书籍大小：{{ normalizedSize }}</span>
        </li>
        <li>
          <span>书籍分类：精彩书籍</span>
        </li>
        <li>
          <span>书籍语言：{{ language }}</span>
        </li>
        <li>
          <span>书籍授权：共享软件</span>
        </li>
        <li>
          <span>更新时间：{{ publishDate }}</span>
        </li>
        <li>
          <span>书籍作者：暂无</span>
        </li>
        <li>
          <span>下载点数：{{ point }}</span>
        </li>
        <li>
          <span>阅读环境：kindle</span>
        </li>
      </ul>
    </el-card>
    <el-card class="box-card product" shadow="never">
      <template #header>
        <div class="card-header">
          <h5 class="title">电子书介绍</h5>
        </div>
      </template>
      <div>
        <el-image
          style=" width: 240px;margin:20px 0 30px;"
          :src="img"
          :alt="alt"
          fit="cover"
        ></el-image>
         <span class="description">{{ description }}</span>
      </div>
    </el-card>
    <el-card class="box-card product" shadow="never">
      <template #header>
        <div class="card-header">
          <h5 class="title">下载地址</h5>
        </div>
      </template>
      <div>
        <ul>
          <li><a href="">{{title}}mobi版</a></li>
          <li><a href="">{{title}}epub版</a></li>
        </ul>
      </div>
    </el-card>
  </div>
</template>
<script>
export default {
  name: "Detail",
  props: {
    title: {
      type: String,
      required: true,
    },
    img: String,
    description: String,
    publishDate: {
      type: String,
      validator(value) {
        return value < new Date();
      },
    },
    point: {
      type: Number,
      default: 0,
    },
    size: {
      type: Number,
      default: 0,
    },
    language: {
      type: String,
      default: "简体中文",
      validator(value) {
        // 这个值必须匹配下列字符串中的一个
        return ["简体中文", "英文"].includes(value);
      },
    },
  },
  computed: {
    normalizedSize() {
      return this.size + "M";
    },
  },
};
</script>

<style scoped>
ul {
  margin: 0;
  padding: 0;
  width: 733px;
  margin: auto;
  text-align: left;
}
li {
  list-style: none;
}
.product-info {
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  width: 100%;
  flex-wrap: wrap;
}
.product-info > li {
  width: 50%;
  flex-shrink: 0;
  text-align: left;
}
.product {
  width: 730px;
}
.title {
  margin: 0;
}
.description {
  text-align: left;
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 7;
  overflow: hidden;
  width: 100%;
  height: 145px;
}
.flex-row-center-between {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
}
.card-header{
  text-align: left;
}
</style>
