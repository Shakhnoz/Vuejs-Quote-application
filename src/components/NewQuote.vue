<template>
  <div class="row d-flex justify-content-center">
    <form>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
        <label>Quote</label>
        <textarea id="textarea" cols="60" rows="3" v-model="quote"></textarea>
      </div>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
        <button class="btn btn-primary" @click.prevent="createNew">Add quote</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      quote: ""
    };
  },
  props: ["quotes"],
  methods: {
    createNew() {
      this.$emit("quoteAdded", this.quote);
      this.quote = "";
    }
  }
};
</script>

<style scoped>
</style>