<template lang="html">

  <div id="educacion" class="container-fluid" style="padding-top:70px;padding-bottom:70px">
    <table class="table text-center">
      <thead class="thead-dark">
        <tr>
          <th v-if="espanol" scope="col">Título</th>
          <th v-if="espanol" scope="col">Lugar</th>
          <th v-if="espanol" scope="col">Fechas</th>
          <th v-if="ingles" scope="col">Title</th>
          <th v-if="ingles" scope="col">Place</th>
          <th v-if="ingles" scope="col">Date</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="dato in datosEducacion" v-bind:key="dato.Titulo">
          <td>{{dato.Titulo}}</td>
          <td>{{dato.Lugar}}</td>
          <td>{{dato.Fecha}}</td>
        </tr>
      </tbody>
    </table>
  </div>

</template>

<script lang="js">

  export default  {
    name: 'educacion',
    props: ["datosEducacion", "espanol", "ingles"],
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
  .educacion {

  }
</style>
