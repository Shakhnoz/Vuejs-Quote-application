<template>
  <div class="col-sm-6 col-md-4 col-lg-3">
    <div class="panel panel-default">
      <div class="panel-body quote border border-success">
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.panel-body {
  font-family: "Arizonia", cursive;
  font-size: 24px;
  color: #18ad99;
  text-align: center;
  margin: 10px;
}

.quote {
  cursor: pointer;
}

.quote:hover {
  background-color: rgb(241, 241, 241);
  border-radius: 2%;
}
</style>