<template>
  <div class="container">
    <app-quotes-number :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-quotes-number>
    <app-new-quote @quoteAdded="newQuote"></app-new-quote>
    <app-quote-grid :quotes="quotes" @deleteQuote="deleteQuote1"></app-quote-grid>
    <div class="row">
      <div class="div col-sm-12 text-center">
        <div class="alert alert-info">Information: Click on a "Quote" to delete it!</div>
      </div>
    </div>
  </div>
</template>

<script>
  import QuoteGrid from './components/QuoteGrid.vue';
  import NewQuote from './components/NewQuote.vue';
  import QuotesNumber from './components/QuotesNumber';


export default {
  data: function() {
    return {
      quotes: [],
      maxQuotes: 10,
    }
  },
  methods: {
    newQuote(quote) {
      if (this.quotes.length >= this.maxQuotes) {
        return alert("Please delete one Quotes first!")
      }
      this.quotes.push(quote)
    },
    deleteQuote1(index) {
      this.quotes.splice(index, 1);
    }
  },
  components: {
    appQuoteGrid: QuoteGrid,
    appNewQuote: NewQuote,
    appQuotesNumber: QuotesNumber
  }
}
</script>

<style>
.alert-info {
  margin-top: 10px;
}
</style>
