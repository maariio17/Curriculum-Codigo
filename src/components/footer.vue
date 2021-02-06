<template lang="html">

    <div id="redesSociales" class="container-fluid" style="padding-top:70px;padding-bottom:70px">
        <section id="footer">
            <div class="color"></div>
            <div class="color"></div>
            <div class="color"></div>
            <ul>
                <li><a href="https://github.com/maariio17"><i class="fab fa-github"></i></a></li>
                <li><a href="https://www.linkedin.com/in/mario-ruiz-a268041a8/"><i class="fab fa-linkedin"></i></a></li>
                <li><a href="https://www.instagram.com/maariio_17/?hl=es"><i class="fab fa-instagram"></i></a></li>
                <li><a href="https://www.facebook.com/maariio17/"><i class="fab fa-facebook-square"></i></a></li>
                <li><a href="https://twitter.com/maariio__17"><i class="fab fa-twitter-square"></i></a></li>
            </ul>
        </section>
    </div>

</template>

<script lang="js">

  export default  {
    name: 'footer',
    props: [],
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
  #footer{
    position: absolute;
    width: 90%;
    height: 15rem;
    display: flex;
    justify-content: center;
    align-items: center;
    }

#footer::before{
    content: '';
    position: absolute;
    width: 100%;
    height: 50%;
    bottom: 0;
    z-index: 10;
    border-top: 1px solid rgba(255,255,255,0.5);
    background:  rgba(255,255,255,0.1);
    backdrop-filter: blur(10px);
}

#footer .color{
    position: absolute;
    filter: blur(150px);
}

#footer ul{
    position: relative;
    display: flex;
}

#footer ul li{
    position: relative;
    list-style: none;
    margin: 10px;
}

#footer ul li a{
    position: relative;
    top: 0;
    width: 50px;
    height: 50px;
    display: flex;
    justify-content: center;
    align-items: center;
    color: #fff;
    font-size: 2em;
    border: 1px solid rgba(0, 0, 0, 0.4);
    border-right: 1px solid rgba(0, 0, 0, 0.2);
    border-bottom: 1px solid rgba(0, 0, 0, 0.2);
    background: rgba(0, 0, 0, 0.1);
    backdrop-filter: blur(4px);
    z-index: 1;
    box-shadow: 0 5px 45px rgba(0, 0, 0, 0.1);
    text-decoration: none;
    overflow: hidden;
    transition: top 0.5s, z-index 0s, transform 0.5s;
    transition-delay: 0.5s, 0.5s, 0s;
}

#footer ul li a:hover{
    transition-delay: 0s, 0.5s, 0.5s;
    top: -50px;
    transform: translateY(50px);
    z-index: 11;
}

#footer ul li a:before{
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 50px;
    height: 100%;
    background: rgba(255,255,255,0.5);
    transform: skewX(45deg) translateX(150px);
    transition: 0.5s;
}

@media (min-width: 768px){
    #footer{
        width: 95%;
    }

    #footer ul li a{
        width: 80px;
        height: 80px;
    }
}

</style>
