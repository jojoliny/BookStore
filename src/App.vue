<template>
  <div>
    <search-box class="searchbox"></search-box>
    <product-list :productList="productList"></product-list>
  </div>
  <!-- <div>
    <detail
        :title="item.title"
        :alt="item.title"
        :img="item.img"
        :publishDate="item.publishTime.substring(0,10)"
        :description="item.description"
      ></detail>
  </div> -->
</template>

<script lang="ts">
import { defineComponent } from "vue";

import ProductList from "./components/product/src/productList.vue";
import SearchBox from "./components/search/src/searchbox.vue";
import Detail from "./components/product/src/detail.vue";

export default defineComponent({
  name: "App",
  components: {
    ProductList,
    SearchBox,
    Detail
  },
  data() {
    return {
      title: "title",
      item:{
          id: 1,
          title: "1234",
          img: "http://www.fast8.com/data/soft_img/1625667059.jpg",
          publishTime: "2021-07-21 22:41:33",
          description:`Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式框架。与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用提供驱动。

如果你想在深入学习 Vue 之前对它有更多了解，我们制作了一个视频，带你了解其核心概念和一个示例工程。`
        }
    };
  },
});
</script>

<style>
.searchbox{
  width: 733px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
