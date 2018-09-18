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
      <Section id="descripcion" style="display: flex; justify-content:center;">
         <TextContent title="Qué es VueJS?">
          Vue.js es un framework progresivo (JavaScript) destinado a la creación de interfaces de usuario. 
          Fue desarrollado inicialmente por Evan You (ex-desarrollador de Google) como una herramienta de prototipado, aparece en el año 2014
          y en la actualidad cuenta con más de 190 personas contribuyendo en la rama core del proyecto. 
        </TextContent>
      </Section>
      <Section id="ventajas">
        <TextContent title= "Ventajas"/>
        <ul> 
          <li>Integra lo mejor de frameworks populares como React, Angular y Ember. Desechando todas las cosas que no aportan al desarrollador.</li>
          <li>Dom Virtual al igual que React, se mantiene un dom en código antes de pintarlo en la pantalla, lo que mejora el rendimiento de la aplicación.</li>
          <li>Componentes reactivos.</li>
          <li>Soporta two-way data binding al igual que Angular lo que sincroniza automáticamente el modelo con el DOM.</li>
          <li>Curva de aprendizaje baja.</li>
          <li>En caso de actualizaciones, Vue solo actualiza aquellos componentes que lo requieran, dejando los demás intactos.</li>
          <li>En el modelo MVC se encarga principalmente de la vista</li>
        </ul>
      </Section>
      <Section id="desventajas">
        <TextContent title= "desVentajas"/>
        <ul> 
          <li>El equipo de desarrollo es relativamente bajo comparado con frameworks como React (193 Vue y 1240 React).</li>
          <li>Menos ofertas laborales que otros frameworks populares.</li>
          <li>Sus herramientas para aplicaciones móviles se encuentran aún en desarrollo.</li>
          <li>No cuenta con el soporte a futuro de alguna compañía grande como lo son Google para angular y Facebook para React.</li>
        </ul>
      </Section>
      <Section id="casos">
        <!--Data binding-->
        <Feature >
                     

          <template slot="description">
             <TextContent title="Data binding">Puede usar la directiva v-model para crear enlaces de datos bidireccionales en la entrada de formulario, área de texto y elementos seleccionados. Selecciona automáticamente la forma correcta de actualizar el elemento en función del tipo de entrada. Aunque un poco mágico, el modelo v es esencialmente azúcar de sintaxis para actualizar los datos de los eventos de entrada del usuario, además de un cuidado especial para algunos casos extremos.
            </TextContent>

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
        <Feature>
          <template slot="description">
            <TextContent title="Conditional rendering"> Para renderizar dependiendo de una varialbe booleana se hace uso de las directivas v-if v-else-if y v-else. Al ser directivas solamente pueden ser asignadas a un único elemento. El efecto de v-if puede ser logrado con v-show, la diferencia es que v-show juega con las propiedades css del elemento, mientras que v-if realmente muestra y oculta totalmente el elemento.
            </TextContent>
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
        <Feature >
          <template slot="description">
            <TextContent title="List rendering">
    Podemos usar la directiva v-for para generar una lista de elementos basada en una matriz. La directiva v-for requiere una sintaxis especial en forma de elemento en los elementos, donde los elementos son la matriz de datos de origen y el elemento es un alias para el elemento de la matriz que se itera en:
    </TextContent>
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
<Feature >
          <template slot="description">
            <TextContent title="Event handling">
Podemos usar la directiva v-on para escuchar eventos DOM y ejecutar JavaScript cuando se desencadenen. Esta directiva permite interacciones principalmente de botones. Puede ser abreviada haciendo uso de '@' en lugar de v-on:.
  </TextContent>
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
<Feature >
          <template slot="description"> 
         <TextContent title="Computed properties">
            Al tratar de insertar código en el template que sea demasiado complejo, puede alentar nuestro programa y puede resultar ser engorroso y desordenado. Usar métodos computados resuelve este problema. Básicamente hace un binding del valor retornado de una función computada.
        </TextContent>

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
import TextContent from "../components/Text-Content.vue";

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
      items: [{ message: "Foo" }, { message: "Bar" }],
      counter: 0,
      text: ""
    };
  },
  computed: {
    reversedText() {
      return this.text
        .split("")
        .reverse()
        .join("");
    }
  },
  components: {
    Header,
    NavBar,
    Section,
    Feature,
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
        this.scrolledNavBarStyle.position = "fixed";
      } else {
        this.scrolledNavBarStyle.position = "relative";
      }
    },
    switchBool() {
      this.showRender = !this.showRender;
    },
    clearNum() {
      this.counter = 0;
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

button{
  
}
</style>
