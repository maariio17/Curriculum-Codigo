<template lang="html">
  <div>
    <div id="habilidades" class="container-fluid" style="padding-top:70px;padding-bottom:70px">
      <ul v-if="espanol" class="list-group">
        <li class="list-group-item" v-for="dato in datosHabilidades" v-bind:key="dato.Habilidad">{{dato.Habilidad}}</li>
      </ul>
      <ul v-if="ingles" class="list-group">
        <li class="list-group-item" v-for="dato in datosHabilidades" v-bind:key="dato.Habilidad">{{dato.Ability}}</li>
      </ul>
    </div>
  </div>

</template>

<script lang="js">

  export default  {
    name: 'habilidades',
    props: ["datosHabilidades", "espanol", "ingles"],
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
  .habilidades {

  }
</style>
