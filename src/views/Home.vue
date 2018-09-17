<template>
  
  <div class = "container">
      <div class="top-container">
             <Header />
             <div class="content">
                <img alt="Vue logo" src="../assets/logo.png">
                <h1> ¿Qué es VueJS?</h1>
             </div>
     </div>
     <div class="bottom-container"></div>
     <NavBar />
    
    <div class="sections-container">
      <Section >    
      </Section>
      <Section >    
      </Section>
     </div>
  </div>
   
</template>

<script>
import Header from "../components/Header.vue";
import NavBar from "../components/NavBar.vue"
import Section from "../components/Section.vue"
import Sections from "../components/Section.vue"
export default {
  name: "Home",
  components: {
    Header,
    NavBar,
    Section
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.container {
  width: 100vw;
}
.top-container {
  background: black;
  height: 100vh;
}
.content {
  height: calc(100vh - 3rem);
  color: white;
  display: flex;
  flex-wrap:wrap;
  justify-content: center;
  align-items: center;
}
.container h1 {
  margin-left: 2%;
  font-size: 4rem;
}
.container .sections-container {
  width:100%;
  display:flex;
  flex-direction: column;
  align-items: center;

}
</style>
