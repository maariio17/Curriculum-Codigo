<template lang="html">

  <div id="idiomas" class="container-fluid" style="padding-top:70px;padding-bottom:70px">
    <div class="progress" v-for="dato in datosIdiomas" v-bind:key="dato.Idioma">
      <div v-if="espanol" class="progress-bar progress-bar-striped progress-bar-animated" role="progressbar" v-bind:style="dato.Style" aria-valuenow="100" aria-valuemin="0" aria-valuemax="100">{{dato.Idioma}}{{dato.Porcentaje}}</div>
      <div v-if="ingles" class="progress-bar progress-bar-striped progress-bar-animated" role="progressbar" v-bind:style="dato.Style" aria-valuenow="100" aria-valuemin="0" aria-valuemax="100">{{dato.Language}}{{dato.Porcentaje}}</div>
    </div>
  </div>

</template>

<script lang="js">

  export default  {
    name: 'idiomas',
    props: ["datosIdiomas", "espanol", "ingles"],
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
  .progress{
    margin: 10px;
    box-shadow: 0px 0px 10px 1px black;
  }
</style>
