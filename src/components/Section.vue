<template>
  <div class="section-content">
      <slot> </slot>
  </div>
</template>

<script>
export default {
  name: "Section"
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.section-content {
  padding: 3rem 5% 0 5%;
  max-width: 1500px;
  width: 100%;
  min-height: 10rem;
  height: calc(100vh - 3rem);
}
</style>
