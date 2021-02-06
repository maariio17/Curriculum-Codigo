<template lang="html">

  <div id="contacto" class="container-fluid" style="padding-top:70px;padding-bottom:70px">
    <form v-if="espanol">
      <div class="form-group">
        <label for="name">Nombre:</label>
        <input type="text" class="form-control" id="name" placeholder="Escribe tu nombre">
      </div>
      <div class="form-group">
        <label for="surname">Apellidos:</label>
        <input type="text" class="form-control" id="surname" placeholder="Escribe tus apellidos">
      </div>
      <div class="form-group">
        <label for="select">Trabajo</label>
        <select class="form-control" id="select">
          <option>Particular</option>
          <option>Empresa</option>
        </select>
      </div>
      <div class="form-group">
        <label for="comment">Comentario</label>
        <textarea class="form-control" id="comment" rows="3" placeholder="Deja aqui tu comentario, por el que quieras contactar conmigo (Gracias)"></textarea>
      </div>
      <button type="submit" class="btn btn-primary">Enviar</button>
    </form>

    <form v-if="ingles">
      <div class="form-group">
        <label for="name">Name:</label>
        <input type="text" class="form-control" id="name" placeholder="Write yout name">
      </div>
      <div class="form-group">
        <label for="surname">Surnames:</label>
        <input type="text" class="form-control" id="surname" placeholder="Write your surnames">
      </div>
      <div class="form-group">
        <label for="select">Work:</label>
        <select class="form-control" id="select">
          <option>Particular</option>
          <option>Company</option>
        </select>
      </div>
      <div class="form-group">
        <label for="comment">Comment</label>
        <textarea class="form-control" id="comment" rows="3" placeholder="Leave your comment here, for which you want to contact me (Thank you)"></textarea>
      </div>
      <button type="submit" class="btn btn-primary">Send</button>
    </form>
   </div>
 

</template>

<script lang="js">

  export default  {
    name: 'contacto',
    props: ["espanol", "ingles"],
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
  form{
    border: 1px solid black;
    padding: 10px;
  }
</style>
