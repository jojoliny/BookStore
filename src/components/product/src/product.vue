<template>
  <div>
    <el-card class="box-card">
      <template #header>
        <div class="card-header flex-row-center-between">
          <span>{{ title }}</span>
          <el-button class="button" type="text">操作按钮</el-button>
        </div>
      </template>
      <div>
        <el-image
          src="https://fuss10.elemecdn.com/e/5d/4a731a90594a4af544c0c25941171jpeg.jpeg"
        ></el-image>
      </div>
    </el-card>
  </div>
</template>
<script>
import { defineComponent } from "vue";
export default defineComponent({
  name: "Product",
  props: {
    title: {
      type: String,
      required: true,
    },
  },
});
</script>

<style scoped>
el-image {
  width: 100px;
  height: 100px;
}
.flex-row-center-between {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
}
</style>
