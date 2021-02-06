<template lang="html">
    <nav class="navbar navbar-expand-lg navbar-light" id="sideNav">  
      <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav mr-auto nav-pills flex-column text-center">
          <div class="d-flex justify-content-center">
              <div id="datosPersonales" v-for="dato in datosPersonales" v-bind:key="dato.Nombre">
                <img v-bind:src="dato.Imagen" class="img rounded-circle" width="140" height="140">
                <h4>{{dato.Nombre}}</h4>
                <p v-if="espanol">{{dato.Edad}}</p>
                <p v-if="ingles">{{dato.Age}}</p>
                <p>{{dato.Fecha}}</p>
                <p>{{dato.Localidad}}</p>
                <p>{{dato.Correo}}</p>
                <p>{{dato.Telefono}}</p>
                <p v-if="espanol">{{dato.Descripcion}}</p>
                <p v-if="ingles">{{dato.Description}}</p>
              </div>
          </div>
          <li class="nav-item" v-for="dato in datosMenu" v-bind:key="dato.Nombre">
            <a v-if="espanol" class="nav-link" v-bind:href="dato.Id">{{dato.Nombre}}</a>
            <a v-if="ingles" class="nav-link" v-bind:href="dato.Id">{{dato.Name}}</a>
          </li>
          <div class="d-flex justify-content-center">
            <div>
              <button id="spain" class="redondo" v-on:click="$emit('cambiarAEspanol')"><img src="Imagenes/spain.png"></button>
              <button id="english" class="redondo2" v-on:click="$emit('cambiarAIngles')"><img src="Imagenes/united-kingdom.png"></button>
            </div>
          </div>
        </ul>
      </div>
    </nav>

</template>

<script lang="js">

  export default  {
    name: 'menulateral',
    props: ["datosPersonales", "datosMenu", "espanol", "ingles"],
    mounted () {

    },
    data () {
      return {
        
      }
    },
    methods: {

    },
    computed: {

    }
}


</script>

<style scoped>
  .redondo {
    display: block;
    width: 24px;
    height: 24px;
    border-radius: 50%;
    border: none;
    margin: 5px 0px;
  }

  .redondo2 {
    display: block;
    width: 24px;
    height: 24px;
    border-radius: 50%;
    border: none;
  }
</style>
