<template>
  <div class="first-component">
    <h3>{{ header }}</h3>

    <div class="custom">
      <a href="/firstComponent.html" v-bind:title="tip">First component</a>
    </div>

    <List v-bind:items="books" title="Available books"/>
  </div>
</template>
<script>
import List from "./List.vue";
export default {
  name: "FirstComponent",
  components: {
    List
  },
  props: {
    header: String,
    tip: String
  },
  data: function() {
      return {
        books: [
          { id: 1231, name: "Arthur Christmas", inStock: 3 },
          { id: 1242, name: "Crazy Rich Asians", inStock: 100 },
          { id: 2353, name: "The subtle art of not giving f*ck", inStock: 45 },
          { id: 1248, name: "You are badass", inStock: 0 },
        ]
      };
  }
};
</script>

<style>
.first-component {
  display: block;
  background-color: lightgray;
  margin-top: 40px;
  padding: 20px 0;
}
.custom {
  padding: 20px 0;
}
.custom > a {
  color: hotpink;
}
</style>