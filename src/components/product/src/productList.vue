<template>
  <ul>
    <li v-for="item in productList" :key="item.id">
      <product
        :title="item.title"
        :alt="item.title"
        :img="item.img"
        :publishDate="item.publishTime.substring(0,10)"
        :description="item.description"
      ></product>
    </li>
  </ul>
</template>
<script>
import product from "./product.vue";
export default {
  name: "ProductList",
  components: {
    product,
  },
  data() {
    return {
      productList: [
        {
          id: 1,
          title: "1234",
          img: "http://www.fast8.com/data/soft_img/1625667059.jpg",
          publishTime: "2021-07-21 22:41:33",
          description:`Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式框架。与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用提供驱动。

如果你想在深入学习 Vue 之前对它有更多了解，我们制作了一个视频，带你了解其核心概念和一个示例工程。`
        },
      ],
    };
  }
};
</script>
<style scoped>
ul {
  margin: 0;
  padding: 0;
  width: 733px;
  margin: auto;
}
li {
  list-style: none;
}
</style>