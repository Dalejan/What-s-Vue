<template>
  <div class="container">
    <div class="top-container">
      <Header />
      <div class="content">
        <img alt="Vue logo" src="../assets/logo.png">
        <h1> ¿Qué es VueJS?</h1>
      </div>
    </div>
    <NavBar v-bind:style="[scrolledNavBarStyle]" />
  
    <div class="sections-container">
      <Section id="descripcion">
        Descripción
      </Section>
      <Section id="ventajas">
        Ventajas
      </Section>
      <Section id="desventajas">
        Desventajas
      </Section>
      <Section id="casos">
        Casos de uso
        <!--Data binding-->
        <Feature name="Data Binding">
          <template slot="description">Puede usar la directiva v-model para crear enlaces de datos bidireccionales en la entrada de formulario, área de texto y elementos seleccionados. Selecciona automáticamente la forma correcta de actualizar el elemento en función del tipo de entrada. Aunque un poco mágico, el modelo v es esencialmente azúcar de sintaxis para actualizar los datos de los eventos de entrada del usuario, además de un cuidado especial para algunos casos extremos.
</template>

<template slot="code">
  &lt;template&gt;
   &lt;input v-model="mensaje" placeholder="Editame"&gt; 
   &lt;p&gt; El mensaje es: &#123; &#123;mensaje&#125; &#125;&lt;/p&gt; 
  &lt;/template&gt; 

   &lt;script&gt;
    data(){
      return { mensaje:''}
    }
   &lt;/script&gt;
</template>

<template slot="example">
  <input v-model="message" placeholder="Editame">
  <p>El mensaje es: {{ message }}</p>

</template>
          </Feature>

          <!--Conditional rendering--> 
        <Feature name="Conditional rendering">
          <template slot="description">Para renderizar dependiendo de una varialbe booleana se hace uso de las directivas v-if v-else-if y v-else. Al ser directivas solamente pueden ser asignadas a un único elemento. El efecto de v-if puede ser logrado con v-show, la diferencia es que v-show juega con las propiedades css del elemento, mientras que v-if realmente muestra y oculta totalmente el elemento.
            
          </template>
<template slot="code">
  &lt;template v-if="showRender === true"&gt;
   &lt;label&gt; Está renderizando &lt;/label&gt;
  &lt;/template &gt;
  &lt;template v-else&gt;
   &lt;label&gt; No está renderizando &lt;/label&gt;
  &lt;/template &gt;

  &lt;script&gt;
    methods:{
        switchBool(){
        this.showRender = !this.showRender;
      }
    }
  &lt;/script&gt;
</template>

<template slot="example">
      <template v-if="showRender === true">
  <label>Está renderizando</label>
</template>
<template v-else>
  <label>No está renderizando</label>
</template>
<button @click="switchBool()">Cambiar estado</button>
  
</template>
          </Feature>

          <!--List rendering-->
        <Feature name="List rendering">
          <template slot="description">
    Podemos usar la directiva v-for para generar una lista de elementos basada en una matriz. La directiva v-for requiere una sintaxis especial en forma de elemento en los elementos, donde los elementos son la matriz de datos de origen y el elemento es un alias para el elemento de la matriz que se itera en:
</template>

<template slot="code">
  &lt;template&gt;
   &lt;input v-model="mensaje" placeholder="Editame"&gt; 
   &lt;p&gt; El mensaje es: &#123; &#123;mensaje&#125; &#125;&lt;/p&gt; 
  &lt;/template&gt; 

   &lt;script&gt;
    data(){
      return { mensaje:''}
    }
   &lt;/script&gt;
</template>

<template slot="example">
<ul >
  <li v-for="item in items">
    {{ item.message }}
  </li>
</ul>
</template>
          </Feature>

          <!--Event handling-->
<Feature name="Event handeling">
          <template slot="description">
Podemos usar la directiva v-on para escuchar eventos DOM y ejecutar JavaScript cuando se desencadenen. Esta directiva permite interacciones principalmente de botones. Puede ser abreviada haciendo uso de '@' en lugar de v-on:.
</template>

<template slot="code">
  &lt;template&gt;
   &lt;button&gt;v-on:click="counter += 1" &lt;/button&gt; 
   &lt;button&gt;@click="clearNum()" &lt;/button&gt; 
   &lt;p&gt; El botón ha sido clickeado &#123; &#123;counter&#125; &#125;&lt;/p&gt; 
  &lt;/template&gt; 

   &lt;script&gt;
   data(){
     return counter:0
   },
   methods:{
     clearNum(){
       this.counter =0;
     }
   }
   &lt;/script&gt;
</template>

<template slot="example">
<div >
  <button v-on:click="counter += 1">Añadir 1</button>  
  <button @click="clearNum()">Limpiar</button>

  <p>El botón ha sido clickeado {{ counter }} veces.</p>
</div>
</template>
          </Feature>

          <!--Computed properties-->
<Feature name="Computed properties">
          <template slot="description"> Al tratar de insertar código en el template que sea demasiado complejo, puede alentar nuestro programa y puede resultar ser engorroso y desordenado. Usar métodos computados resuelve este problema. Básicamente hace un binding del valor retornado de una función computada.
</template>

<template slot="code">
  &lt;template&gt;
   &lt;input&gt;v-model="text"&lt;/input&gt; 
   &lt;p&gt; Mensaje &#123; &#123;text&#125; &#125;&lt;/p&gt; 
   &lt;p&gt; Mensaje Voltiao' &#123; &#123;reversedText&#125; &#125;&lt;/p&gt; 
  &lt;/template&gt; 

   &lt;script&gt;
   data(){
     return text:""
   },
   computed(){
     reversedText(){
      return this.text.split('').reverse().join('');
    }
   }
   &lt;/script&gt;
</template>

<template slot="example">
<div>
  <input v-model="text">
  <p>Mensaje: "{{ text }}"</p>
  <p>Mensaje Voltiao' "{{ reversedText }}"</p>
</div>
</template>
          </Feature>

        </Section>
     </div>
  </div> 
</template>
 
<script>

import Header from "../components/Header.vue";
import NavBar from "../components/NavBar.vue";
import Section from "../components/Section.vue";
import Feature from "../components/FeatureComponent/Feature.vue";

export default {
  name: "Home",
  data() {
    return {
      scrolledNavBarStyle: {
        position: "relative",
        background: "white",
        top: 0,
        bottom: 0
      },
      message: " ",
      showRender: true,
      items:[
         { message: 'Foo' },
      { message: 'Bar' }
      ],
      counter: 0,
      text:""
    };
  },
  computed:{
    reversedText(){
      return this.text.split('').reverse().join('');
    }
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
        this.scrolledNavBarStyle.position = "fixed";
      } else {
        this.scrolledNavBarStyle.position = "relative";
      }
    },
    switchBool(){
      this.showRender = !this.showRender;
    },
    clearNum(){
      this.counter =0;
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
