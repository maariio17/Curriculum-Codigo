<template lang="html">

  <div id="proyectos" class="container-fluid" style="padding-top:70px;padding-bottom:70px">
    <div class="row">
      <div v-for="dato in datosProyectos" v-bind:key="dato.Titulo" class="col-12 col-lg-4">
        <div class="card-deck">
          <div class="card">
            <img v-bind:src=dato.ImagenProyecto class="card-img-top " alt="Imagen Proyecto">
            <div class="card-body">
              <h5 class="card-title d-flex justify-content-center">{{dato.Titulo}}</h5>
            </div>
            <div class="card-footer">
              <small class="text-muted d-flex justify-content-center">
                <a v-if="espanol" class="btn btn-primary" data-toggle="modal" v-bind:data-target=dato.Id href="#" role="button">Saber más ...</a>
                <a v-if="ingles" class="btn btn-primary" data-toggle="modal" v-bind:data-target=dato.Id href="#" role="button">More Info ...</a>
              </small>
            </div>
          </div>
          <!--Modal-->
          <div class="modal fade" v-bind:id=dato.Titulo tabindex="-1" role="dialog" aria-labelledby="exampleModalCenterTitle" aria-hidden="true">
            <div class="modal-dialog modal-dialog-centered modal-lg" role="document">
              <div class="modal-content">
                <div class="modal-header">
                  <h5 class="modal-title" id="ModalTitle">{{dato.Titulo}}</h5>
                  <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                    <span aria-hidden="true">&times;</span>
                  </button>
                </div>
                <div class="modal-body">
                  <div class="row">
                    <div class="col-6 imagenesProyecto">
                      <img v-bind:src=dato.ImagenProyecto class="card-img-top " alt="Imagen Proyecto">
                      <img v-bind:src=dato.Imagen2 class="card-img-top " alt="Imagen Proyecto">
                      <img v-bind:src=dato.Imagen3 class="card-img-top " alt="Imagen Proyecto">
                    </div>
                    <div class="col-6 datosProyecto">
                      <p><b>Link Produccion:</b> <a v-bind:href=dato.LinkProduccion>{{dato.LinkProduccion}}</a></p>
                      <p><b>Link Repositorio:</b> <a v-bind:href=dato.LinkRepositorio>{{dato.LinkRepositorio}}</a></p>
                      <p v-if="espanol"><b>Resumen:</b> {{dato.Resumen}}</p>
                      <p v-if="ingles"><b>Summary:</b> {{dato.Summary}}</p>
                      <p v-if="espanol"><b>Tecnologías Aplicadas:</b> {{dato.Tecnologias}}</p>
                      <p v-if="ingles"><b>Applied Technologies:</b> {{dato.Tecnologias}}</p>
                    </div>
                  </div>
                </div>
                <div class="modal-footer">
                  <button v-if="espanol" type="button" class="btn btn-secondary" data-dismiss="modal">Cerrar</button>
                  <button v-if="ingles" type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>    

</template>

<script lang="js">

  export default  {
    name: 'proyectos',
    props: ["datosProyectos", "espanol" ,"ingles"],
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
  .cardProyectos{
    text-align: center;
  }

  .proyectos{
    box-shadow: 0px 0px 10px 1px white;
    background: rgba(0, 0, 0, 0.4);
    color: white;
    font-family: 'Londrina Solid', cursive;
  }

  .imagenesProyecto > img{
      margin-bottom: 5px;
      object-fit: cover;
  }

  .datosProyecto a {
    word-wrap: break-word;
  }
</style>
