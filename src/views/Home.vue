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
    
    <div class="sections-container" >
        <Section id="descripcion" >  
          <TextContent title="Mi título" subtitle="Mi subtítulo" >
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce scelerisque lacus eget arcu fermentum fermentum. Nullam mi tellus, 
          consequat vestibulum ipsum sed, suscipit viverra dolor. Nam ac ornare ex. Mauris vitae enim erat. Integer faucibus pulvinar lectus, 
          vitae fermentum lectus. Ut auctor pretium enim eu ullamcorper. Fusce faucibus ultricies nibh, in imperdiet risus pharetra ullamcorper.
          Nam vestibulum ipsum erat, sed imperdiet lacus elementum non. Quisque sed felis faucibus, pharetra diam vitae, gravida lectus. 
          Quisque ornare porta orci. Vestibulum ultricies elementum mi et viverra. Aliquam fermentum, enim sit amet consectetur ullamcorper, 
          dolor sapien ultricies nisl, non suscipit neque mauris a ex.
        </TextContent>
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
import Sections from "../components/Section.vue"
import TextContent from "../components/Text-Content.vue"

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
    TextContent
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
