<template>
  <div id="items-list">
    <h4>{{ title }}</h4>
    <div v-if="notEmpty">
      <button v-on:click="sortName">Sort By Name</button>
      <button v-on:click="sortQuantity">Sort By Quantity</button>
      <ul>
        <li v-for="book in items" v-bind:key="book.id">
          <span v-bind:class="{sold: book.inStock <= 0}">{{ book.name }} - {{ book.inStock }}</span>
        </li>
      </ul>
    </div>

    <span v-else class="not-found-row">No books found</span>
  </div>
</template>

<script>
export default {
  name: "List",
  props: {
    title: String,
    items: Array
  },
  data: function() {
    return {
      notEmpty: this.items && this.items.length > 0
    };
  },
  methods: {
    sortName: function() {
      this.items.sort(function(a, b) {
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
      this.items.sort(function(a, b) {
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
#items-list li {
  font-size: 0.9em;
}
#items-list li > .sold {
  text-decoration: line-through;
}
.not-found-row {
  font-size: 0.8em;
  font-style: italic;
}
</style>