<script> 
  // importo il componente
  import HeaderBoolando from "./components/HeaderBoolando.vue";
  import MainBoolando from "./components/MainBoolando.vue";
  import FooterBoolando from "./components/FooterBoolando.vue";
  
  export default{
    data(){
      return{

      }
    },
    components:{
      HeaderBoolando,
      MainBoolando,
      FooterBoolando
    }
  }

</script>

<template>
  <div class="container">
    <div class="row page">
      <header class="col page-header">
        <HeaderBoolando/>
      </header>
      <main class="col page-main">
        <MainBoolando/>
      </main>
      <footer class="col page-footer">
        <FooterBoolando/>
      </footer>
    </div>
  </div>
</template>

<style lang="scss">
  @use './style/general.scss';
  @use './style/partials/utilities.scss' as *;

  .row.page{
    flex-direction: column;
    height: 100vh;
  }

  .col.page-header{
    background-color: $header-background-color;
  }

  .col.page-main{
    flex-grow: 1;
  }

  .col.page-footer{
    background-color: $footer-background-color;
  }



</style>