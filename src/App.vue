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

  .row.page{
    flex-direction: column;
    height: 100vh;
  }

  .col.page-main{
    flex-grow: 1;
  }
</style>