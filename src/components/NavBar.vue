<template>
  <div class = "navBar">
      <div class="item active">
          Descripción
      </div>
      <div class="item">
         Ventajas
      </div>
      <div class="item">
          Desventajas
      </div>
      <div class="item">
          Casos de uso
      </div>
  </div>
</template>

<script>
export default {
  name: "NavBar"
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.navBar {
  width: 100%;
  height: 3rem;
  display: flex;
  flex-wrap:wrap;
  justify-content: space-between;
  align-items: center;
  font-weight: 600;
  font-size: 1.1rem;
  padding: 0 1rem;
  padding: 0 25%;
  background: transparent;
}
.navBar .item {
    font-size: 1.2em;
    height: 1.3em;
}
.navBar .item:hover {
  cursor: pointer;
  border-bottom: 3px solid #42b983;
}
</style>
