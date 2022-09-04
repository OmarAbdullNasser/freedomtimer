<template>
  <nav class="container align-items-center mb-5">
    <div class="row d-flex align-items-center justify-content-between ">
      <div class="logo col-md-6">
          <img src="../src/assets/stopwatch2.png"  alt="">
          <span>FreedomTimer</span>
    </div>
    <div class="icons col-md-6 d-flex justify-content-center mt-md-0 mt-3  ">
      <div class="icon mx-3 px-3">
        <a href="https://twitter.com/o_abdullnasser">
          <fa icon="fa-brands fa-twitter" />
        </a>
      
      </div>
      <div class="icon mx-3 px-3">
        <a href="https://www.facebook.com/omar.abdulnasser.9822/">
          <fa icon="fa-brands fa-facebook-f"/>
        </a>
      </div>
      <div class="icon mx-3 px-3">
        <a href="https://github.com/OmarAbdullNasser">
          <fa icon="fa-brands fa-github" />
        </a>
      </div>

    </div>
    </div>
  </nav>




  <HomeView class="container"/>



  <!--
    #d78d5e
    #2c4d6e
    #d6cea4
    #223640
    #c93e27
    #fffefd
    #170010
  -->
</template>



<script>
  // @ is an alias to /src
  import HomeView from '@/views/HomeView.vue'
  
  export default {
    name: 'app',
    components: {
    HomeView,
}
  }
  </script>
  
<style lang="scss">
  body{
    background-color: #2c4d6e !important;
  //  background-image: linear-gradient( #c93e27 80%,#fffefd);
  //  min-height: 100vh;
                                                
  }
#app {
  font-family: 'Roboto Mono', monospace;
  
  text-align: center;
  color: #2c3e50;
  
}

nav {
  padding: 15px;
.logo{
  margin-top: 10px;
  text-align: center;
    img{
      width:70px;
      height:70px;
      }
      span{
        font-size: 30px;
        font-weight: bolder;
        margin: 10px;
        color: #fffefd;
        
      }
  }
  .icons{
    font-size: 25px;
    .icon{
      a{
        text-decoration: none;
        color:#fff
      }
      border-radius: 50%;
      background-color:rgba(255, 255, 255, .1) ;
      padding: 10px;
      
    }
  }
}
</style>
