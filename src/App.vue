<template>
  <Home />
  
</template>

<script>
import Home from "./views/Home.vue";

export default {
  name: "app",
  components: {
    Home
  }
};
</script>
<style>
* {
  box-sizing: border-box;
}
html {
  font-size: 1.2vw;
}

body {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin: 0;
  padding: 0;
  color: #2c3e50;
  overflow-x: hidden;
}

a {
    text-decoration: none;
    color: inherit;
}
::-webkit-scrollbar {
  width: 3px;
  background-color: #f5f5f5;
}
::-webkit-scrollbar-thumb {
  background-color: #42b983;
}
::-webkit-scrollbar-track {
  -webkit-box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.3);
  box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.3);
  background-color: #f5f5f5;
}
</style>
