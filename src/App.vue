<template>
  <div class="container">
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <app-new-quote @quoteAdded="newQuote"></app-new-quote>
    <app-quotes-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quotes-grid>
    <div class="row">
      <div class="col-sm-12" text-center>
        <div class="alert alert-info">Click on a quote to delete it </div>
      </div>
      <div class="col-sm-12" text-center>
        <div class="alert alert-info">
         <div :alertQuotes="alertQuotes"> </div> 
        </div>
      </div>       
    </div>
  </div>
</template>
<script>
  import QuotesGrid from './components/QuotesGrid'
  import NewQuote from './components/NewQuote'
  import Header from './components/Header'
  export default {
    data: function () {
      return {
        quotes: [
          'Type your own quote'
        ],
        maxQuotes: 10,
        alertQuotes: ''
      }
    },
    methods: {
      newQuote(quote) {
        if(this.quotes.length>=this.maxQuotes){
          
           return console.log('Pleace, delete quote at first!')
          
        }
        this.quotes.push(quote)
      },
      deleteQuote(i) {
        this.quotes.splice(i, 1)
      }
    },
    components: {
      appQuotesGrid: QuotesGrid,
      appNewQuote: NewQuote,
      appHeader: Header
    }
  }
</script>
<style>
</style>