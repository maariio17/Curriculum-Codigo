<template lang="html">

  <div id="referencias" class="container-fluid" style="padding-top:70px;padding-bottom:70px">
    <div class="container-fluid referencias">
        <div class="hexagon" v-for="dato in datosReferencias" v-bind:key="dato.Nombre">
            <div class="shape">
                <img v-bind:src="dato.Imagen">
                <div class="content">
                    <div>
                        <h2 v-if="espanol">{{dato.Nombre}}</h2>
                        <p v-if="espanol">{{dato.Referencia}}</p>
                        <h2 v-if="ingles">{{dato.Nombre}}</h2>
                        <p v-if="ingles">{{dato.Reference}}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
  </div>

</template>

<script lang="js">

  export default  {
    name: 'referencias',
    props: ["datosReferencias", "espanol", "ingles"],
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
  .referencias{
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
}

.referencias .hexagon{
    position: relative;
    width: 300px;
    height: 350px;
    margin: 50px 20px 70px;
}

.referencias .hexagon::before{
    content: '';
    position: absolute;
    bottom: -70px;
    width: 100%;
    height: 60px;
    background: radial-gradient(rgba(0,0,0,0.15), transparent);
    border-radius: 50%;
    transition: 0.5s;
}

.referencias .hexagon:hover::before{
    opacity: 0.8;
    transform: scale(0.8);
}

.referencias .hexagon .shape{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: #000;
    clip-path: polygon(0 26%, 51% 0, 100% 26%, 100% 74%, 51% 100%, 0 74%);
    transition: 0.5s;
}

.referencias .hexagon:hover .shape{
    transform: translateY(-30px);
}

.referencias .hexagon .shape img{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.referencias .hexagon .shape .content{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 20px;
    text-align: center;
    background: linear-gradient(45deg, #03a9f4, rgba(3,169,244,0.5));
    color: #fff;
    opacity: 0;
    transition: 0.5s;

}

.referencias .hexagon:hover .shape .content{
    opacity: 1;
}

@media (min-width: 768px) {
    .referencias .hexagon{
        position: relative;
        width: 350px;
        height: 400px;
        margin: 50px 20px 70px;
    }
}
</style>
