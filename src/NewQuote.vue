<template>
  <form>
    <div class="row">
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
        <label>Quote</label>
        <textarea class="form-control" rows="3" v-model="quote"></textarea>
      </div>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
        <button v-if="quotes.length < maxQuotes" class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
        <div class="alert alert-danger" v-else>You have do delete some Quotes first to add new ones!</div>
      </div>
    </div>
  </form>
</template>

<script>
export default {
    props: ['quotes', 'maxQuotes'],
    data: function() {
        return {
            quote: ''
        }
    },
    methods: {
        createNew(){
            if(this.quote != ''){
                this.$emit('addedQuote', this.quote);
            };
            
        }
    }
};
</script>

<style>
</style>

