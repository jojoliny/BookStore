<template>
  <div>
    <search-box class="searchbox"></search-box>
    <product-list :productList="productList"></product-list>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

import ProductList from "./components/product/src/productList.vue";
import SearchBox from "./components/search/src/searchbox.vue";
export default defineComponent({
  name: "App",
  components: {
    ProductList,
    SearchBox,
  },
  data() {
    return {
      title: "title",
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
