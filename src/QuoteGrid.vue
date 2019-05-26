<template>
  <div class="row">
      <quote v-for="(quote, i) in quotes" v-bind:key="i" @click.native="deleteQuote(i)">
        <p>{{quote}}</p>
      </quote>
  </div>
</template>

<script>
import Quote from "./Quote.vue";

export default {
  components: {
    Quote
  },
  props: ['quotes'],
  methods: {
    deleteQuote(index){
      this.$emit('quoteToDelete', index)
    }
  }
};
</script>

<style>
</style>