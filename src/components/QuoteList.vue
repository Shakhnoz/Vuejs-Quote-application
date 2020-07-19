<template>
  <div>
    <div class="row">
      <quote v-for="(quote, index) in quotes" @click.native="deleteQuote(index)">{{quote}}</quote>
    </div>
  </div>
</template>

<script>
import Quote from "@/components/Quote.vue";
export default {
  props: ["quotes"],
  components: {
    Quote
  },
  methods: {
    deleteQuote(index) {
      this.$emit("quoteDeleted", index);
    }
  }
};
</script>

<style scoped>
</style>