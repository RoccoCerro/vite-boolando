<script>
// importo il componente
import HeaderBoolando from "./components/HeaderBoolando.vue";
import MainBoolando from "./components/MainBoolando.vue";
import FooterBoolando from "./components/FooterBoolando.vue";
import { store } from './store.js';
import axios from 'axios';

export default {
  data() {
    return {
      store
    }
  },
  methods: {
    fetchTodos() {
      axios.get('http://localhost:3000/products').then((res) => {
        this.store.clothes = res.data
      })
    }
  },
  created: function () {
    this.fetchTodos()
  },
  components: {
    HeaderBoolando,
    MainBoolando,
    FooterBoolando
  }
}

</script>

<template>
  <div class="row page">
    <header class="col page-header">
      <HeaderBoolando />
    </header>
    <main class="col page-main">
      <MainBoolando />
    </main>
    <footer class="col page-footer">
      <FooterBoolando />
    </footer>
  </div>
</template>

<style lang="scss">
@use './style/general.scss';
@use './style/partials/utilities.scss' as *;
</style>