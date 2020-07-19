<template>
  <div class="container">
    <Header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></Header>
    <NewQuote @quoteAdded="newQuote"></NewQuote>
    <QuoteList :quotes="quotes" @quoteDeleted="deleteQuote"></QuoteList>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Info: Click on a Quote to delete it!</div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteList from "@/components/QuoteList.vue";
import NewQuote from "@/components/NewQuote.vue";
import Header from "@/components/Header.vue";
export default {
  data() {
    return {
      quotes: ["Sample quote"],
      maxQuotes: 10
    };
  },
  components: {
    QuoteList,
    NewQuote,
    Header
  },
  methods: {
    newQuote(quote) {
      if (quote.trim().length == 0) {
        return alert("A quote cannot be empty");
      } else if (this.quotes.length >= this.maxQuotes) {
        return alert("Please, delete the Quotes first!");
      }
      this.quotes.push(quote);
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
    }
  }
};
</script>

<style scoped>
.container {
  max-width: 1140px;
  margin: 30px auto;
}
</style>