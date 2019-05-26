<template>
  <div class="container">
    <progressBar v-bind:quoteCount="quotes.length" v-bind:maxQuotes="maxQuotes"></progressBar>
    <new-quote v-on:addedQuote="addQuote" v-bind:quotes="quotes" v-bind:maxQuotes="maxQuotes"></new-quote>
    <quote-grid v-bind:quotes="quotes" v-on:quoteToDelete="deleteQuote"></quote-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">
          Info: Click on a Quote to delete it!
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from "./QuoteGrid.vue";
import NewQuote from "./NewQuote.vue";
import progressBar from "./Header.vue";

export default {
  components: {
    QuoteGrid,
    NewQuote,
    progressBar
  },
  data: function() {
    return {
      quotes: [
        "When you find yourself stuck in a hole, the best thing you can do is stop digging."
      ],
      maxQuotes: 10,
    };
  },
  methods: {
    addQuote(quote) {
      this.quotes.push(quote)
    },
    deleteQuote(index){
      this.quotes.splice(index, 1);
    }
  }
}
</script>

<style>
</style>
