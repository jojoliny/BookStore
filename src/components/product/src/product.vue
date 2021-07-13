<template>
  <el-card class="box-card product">
    <template #header>
      <div class="card-header flex-row-center-between">
        <h5 class="title">{{ title }}</h5>
        <span>{{publishDate}}</span>
        <!-- <el-button class="button" type="text">前往下载</el-button> -->
      </div>
    </template>
    <el-row :gutter="24">
      <el-col :span="5">
        <el-image style="width: 135px;height: 145px;" :src="img" :alt="alt" fit="cover"></el-image>
      </el-col>
      <el-col :span="19">
        <span class="description">{{description}}</span>
      </el-col>
    </el-row>
  </el-card>
</template>
<script>
export default {
  name: "Product",
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
  },
};
</script>

<style scoped>
.product {
  width: 730px;
  cursor: pointer;
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
el-image {
  width: 135px;
  height: 145px;
}
.flex-row-center-between {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
}
</style>
