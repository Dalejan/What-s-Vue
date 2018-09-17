<template>
  <div class = "header">
      <div class="item">
          Inicio
      </div>
      <div class="item">
          Tutorial
      </div>
  </div>
</template>

<script>
export default {
  name: "Header"
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header {
  width: 100%;
  height: 3rem;
  display: flex;
  font-size: 1.5rem;
  padding: 0 1rem;
  background: transparent;
}
.header .item {
  display:inline;
  padding-right: 4%;
  color: rgba(255, 255, 255, 0.3);
  transition: background 400ms ease-in-out;
}
.header .item:hover {
    
  color: rgba(255, 255, 255, 0.8);
  cursor:pointer;
}
</style>
