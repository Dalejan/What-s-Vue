<template>
  <div class = "header">
      <div class="item">
          INICIO
      </div>
      <div class="item">
          <a href="https://vuejs.org/v2/guide/installation.html">TUTORIAL</a>
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
  height: 2rem;
  display: flex;
  align-items: center;
  font-weight: 600;
  font-size: 1.1rem;
  padding: 0 1rem;
  background: transparent;
}
.header .item {
  margin-right: 4%;
  height: 1.4em;
  color: rgba(255, 255, 255, 0.3);
  transition: background 400ms ease-in-out;
}
.header .item:hover {
  color: rgba(255, 255, 255, 0.8);
  cursor: pointer;
  border-bottom: 3px solid #42b983;
}
</style>
