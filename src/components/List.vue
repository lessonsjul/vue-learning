<template>
  <div id="items-list">
    <button v-on:click="sortName">Sort By Name</button>
    <button v-on:click="sortQuantity">Sort By Quantity</button>
    <ul v-if="seen">
      <li v-for="book in items" v-bind:key="book.id">
        {{ book.name }} - {{ book.inStock }}
        </li>
    </ul>
    <span v-else>No books found</span>
  </div>
</template>

<script>
export default {
  name: "List",
  props: {
    items: Array
  },
  methods: {
    seen: function() {
      return this.items && this.items.length > 0;
    },
    sortName: function() {
      this.items.sort(function (a, b) {
          if (a.name > b.name) {
            return 1;
          }
          if (a.name < b.name) {
            return -1;
          }
          // a должно быть равным b
          return 0;
        });
    },
    sortQuantity: function() {
      this.items.sort(function (a, b) {
          if (a.inStock > b.inStock) {
            return 1;
          }
          if (a.inStock < b.inStock) {
            return -1;
          }
          // a должно быть равным b
          return 0;
        });
    }
  }
};
</script>

<style>
/* #books-list{ */
/* display: block; */
/* width: 40px; */
/* height: 50px; */
/* background-color: red */
/* } */
</style>