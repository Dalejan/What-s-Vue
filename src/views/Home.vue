<template>
  
  <div class = "container"   >
      <div class="top-container" >
             <Header />
             <div class="content">
                <img alt="Vue logo" src="../assets/logo.png">
                <h1> ¿Qué es VueJS?</h1>
             </div>
     </div>
     <NavBar v-bind:style="[scrolledNavBarStyle]"/>
    
    <div class="sections-container">
      <Section >    
      </Section>
      <Section >    
              <Feature name="Paco"/>

      </Section>
    <div class="sections-container" >
        <Section id="descripcion" >  
          Descripción  
        </Section>
        <Section id="ventajas" > 
          Ventajas
        </Section>
        <Section  id="desventajas" > 
          Desventajas
        </Section>
        <Section id="casos" > 
          Casos de uso
        </Section>
     </div>
  </div>
   
</template>

<script>
import Header from "../components/Header.vue";
import NavBar from "../components/NavBar.vue"
import Section from "../components/Section.vue"
import Feature from "../components/FeatureComponent/Feature.vue"

export default {
  name: "Home",
  data() {
    return {
      scrolledNavBarStyle : {
        position: 'relative',
        background: 'white',
        top: 0,
        bottom: 0
      }
    };
  },
  components: {
    Header,
    NavBar,
    Section,
    Feature
  },
  mounted() {
    window.addEventListener("scroll", this.navBarScrollHandler);
  },
  destroyed: () => {
    window.removeEventListener("scroll", this.navBarScrollHandler);
  },
  methods: {
    navBarScrollHandler() {
      if (window.scrollY > window.innerHeight) {
        this.scrolledNavBarStyle.position = "fixed"
      }
      else{
        this.scrolledNavBarStyle.position = "relative"
      }
    }
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
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
}
.container h1 {
  margin-left: 2%;
  font-size: 4rem;
}
.container .sections-container {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
