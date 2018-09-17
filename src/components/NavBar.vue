<template>
  <div class = "navBar">
      
      <div class="item active">
         <a href="#descripcion">Descripción </a>
      </div>
      <div class="item">
        <a href="#ventajas">Ventajas </a>
      </div>
      <div class="item">
          <a href="#desventajas">Desventajas </a>
      </div>
      <div class="item">
          <a href="#casos">Casos de uso</a>
          
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
