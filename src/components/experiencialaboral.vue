<template lang="html">

  <div id="experienciaLaboral" class="container-fluid" style="padding-top:70px;padding-bottom:70px">
    <div class="row">
      <div class="col-12 col-lg-12">
        <section class="container-fluid">
          <div class="card-deck">
            <div class="card" v-for="dato in datosExperienciaLaboral" v-bind:key="dato.Trabajo">
              <img v-bind:src=dato.Imagen class="card-img-top " style="height: 200px; object-fit: cover;" alt="gato de Alicia">
              <div class="card-body">
                <h5 v-if="espanol" class="card-title">{{dato.Trabajo}}</h5>
                <p v-if="espanol" class="card-text">{{dato.Fecha}}</p>
                <p v-if="espanol" class="card-text">{{dato.Descripcion}}</p>
                <h5 v-if="ingles" class="card-title">{{dato.Work}}</h5>
                <p v-if="ingles" class="card-text">{{dato.Date}}</p>
                <p v-if="ingles" class="card-text">{{dato.Description}}</p>
              </div>
              <div class="card-footer">
              </div>
            </div>
          </div>
        </section>
      </div>
    </div>   
  </div>

</template>

<script lang="js">

  export default  {
    name: 'experiencialaboral',
    props: ["datosExperienciaLaboral", "espanol", "ingles"],
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
  .card{
    margin: 10px;
    box-shadow: 0px 0px 10px 1px black;
    /*height: min-content;*/
  }

</style>
