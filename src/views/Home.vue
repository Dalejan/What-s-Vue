<template>
  
  <div class = "container">
    <Header />
    <div class="content">
        <img alt="Vue logo" src="../assets/logo.png">
    <h1> ¿Qué es VueJS?</h1>
    </div>
    
  </div>
</template>

<script>
import Header from "../components/Header.vue";
export default {
  name: "Home",
  components: {
    Header
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  height: 100vh;
  width: 100vw;
  background: black;
}
.content {
  height: calc(100vh - 3rem);
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
}
.container h1 {
  margin-left: 2%;
  font-size: 3rem;
}
</style>
