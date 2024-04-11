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
</template>

<style lang="scss">
  @use './style/general.scss';
  @use './style/partials/utilities.scss' as *;

  .row.page{
    flex-direction: column;
  }

  .col.page-header{
    background-color: $header-background-color;
    min-height: 60px;
    color: white;
  }

  .col.page-main{
    flex-grow: 1;
  }

  .col.page-footer{
    background-color: $footer-background-color;
    color: white;
    min-height: 60px;
  }

</style>