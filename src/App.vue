<template>
  <div id="app" class="container-fluid">
    <div v-if="datos">
      <div class="row">
        <div class="col-12 col-lg-3">
          <Menulateral v-bind:datosPersonales="datos.DatosPersonales" v-bind:datosMenu="datos.Menu" v-bind:espanol="espanol" v-bind:ingles="ingles" v-on:cambiarAEspanol="cambiarAEspanol" v-on:cambiarAIngles="cambiarAIngles"/>
        </div>
        <div class="col-12 col-lg-9">
          <h1 v-if="espanol">{{datos.Menu && datos.Menu.length > 0 ? datos.Menu[0].Nombre : ''}}</h1>
          <h1 v-if="ingles">{{datos.Menu && datos.Menu.length > 0 ? datos.Menu[0].Name : ''}}</h1>
          <Experiencialaboral v-bind:datosExperienciaLaboral="datos.ExperienciaLaboral" v-bind:datosMenu="datos.Menu" v-bind:espanol="espanol" v-bind:ingles="ingles"/>
          <h1 v-if="espanol">{{datos.Menu && datos.Menu.length > 0 ? datos.Menu[1].Nombre : ''}}</h1>
          <h1 v-if="ingles">{{datos.Menu && datos.Menu.length > 0 ? datos.Menu[1].Name : ''}}</h1>
          <Educacion v-bind:datosEducacion="datos.Educacion" v-bind:espanol="espanol" v-bind:ingles="ingles"/>
          <h1 v-if="espanol">{{datos.Menu && datos.Menu.length > 0 ? datos.Menu[2].Nombre : ''}}</h1>
          <h1 v-if="ingles">{{datos.Menu && datos.Menu.length > 0 ? datos.Menu[2].Name : ''}}</h1>
          <Habilidades v-bind:datosHabilidades="datos.Habilidades" v-bind:espanol="espanol" v-bind:ingles="ingles"/>
          <h1 v-if="espanol">{{datos.Menu && datos.Menu.length > 0 ? datos.Menu[3].Nombre : ''}}</h1>
          <h1 v-if="ingles">{{datos.Menu && datos.Menu.length > 0 ? datos.Menu[3].Name : ''}}</h1>
          <Proyectos v-bind:datosProyectos="datos.Proyectos" v-bind:espanol="espanol" v-bind:ingles="ingles"/>
          <h1 v-if="espanol">{{datos.Menu && datos.Menu.length > 0 ? datos.Menu[4].Nombre : ''}}</h1>
          <h1 v-if="ingles">{{datos.Menu && datos.Menu.length > 0 ? datos.Menu[4].Name : ''}}</h1>
          <Idiomas v-bind:datosIdiomas="datos.Idiomas" v-bind:espanol="espanol" v-bind:ingles="ingles"/>
          <h1 v-if="espanol">{{datos.Menu && datos.Menu.length > 0 ? datos.Menu[5].Nombre : ''}}</h1>
          <h1 v-if="ingles">{{datos.Menu && datos.Menu.length > 0 ? datos.Menu[5].Name : ''}}</h1>
          <Referencias v-bind:datosReferencias="datos.Referencias" v-bind:espanol="espanol" v-bind:ingles="ingles"/>
          <h1 v-if="espanol">{{datos.Menu && datos.Menu.length > 0 ? datos.Menu[6].Nombre : ''}}</h1>
          <h1 v-if="ingles">{{datos.Menu && datos.Menu.length > 0 ? datos.Menu[6].Name : ''}}</h1>
          <Contacto v-bind:espanol="espanol" v-bind:ingles="ingles"/>
          <h1 v-if="espanol">{{datos.Menu && datos.Menu.length > 0 ? datos.Menu[7].Nombre : ''}}</h1>
          <h1 v-if="ingles">{{datos.Menu && datos.Menu.length > 0 ? datos.Menu[7].Name : ''}}</h1>
          <Footer/>
        </div>
      </div>
    </div>
    
    <div v-if="!datos" class="container-fluid">
      <Loading/>
    </div>
  </div>
</template>

<script>

import Menulateral from './components/menulateral.vue'
import Experiencialaboral from './components/experiencialaboral.vue'
import Educacion from './components/educacion.vue'
import Habilidades from './components/habilidades.vue'
import Proyectos from './components/proyectos.vue'
import Idiomas from './components/idiomas.vue'
import Referencias from './components/referencias.vue'
import Contacto from './components/contacto.vue'
import Footer from './components/footer.vue'
import Loading from './components/loading.vue'

export default {
  name: 'App',
  components: {
    Menulateral,
    Experiencialaboral,
    Educacion,
    Habilidades,
    Proyectos,
    Idiomas,
    Referencias,
    Contacto,
    Footer,
    Loading
  },
  mounted () {
      this.axios.get("datos.json").then((response) => {
        this.datos = response.data;
      })
      .catch(function(error){
        console.log(error);
      })
    },
    data () {
      return {
        datos: null,
        espanol: true,
        ingles: false
      }
    },
    methods: {
      cambiarAIngles: function () {
        this.ingles = true;
        this.espanol = false;
      },
      cambiarAEspanol: function () {
        this.ingles = false;
        this.espanol = true;
      }
    }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

.card-deck {
  flex-direction: column;
}


/*tablets*/
@media (min-width: 768px) {
  .card-deck {
    flex-direction: row;
    flex-wrap: wrap;
  }
}


@media (min-width: 992px) {
    #sideNav{
        text-align: center;
        position: fixed;
        top: 0;
        left: 5%;
        display: flex;
        flex-direction: column;
        width: 15vw;
        height: 100vh;
    }
}
</style>