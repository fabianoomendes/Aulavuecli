<template>
  <div class="body">
    <MeuComponente/>
  </div>
</template>

<script>

import MeuComponente from './components/MeuComponente.vue'
import Header from './components/Header.vue'
import ComponenteTeste from './components/ComponenteTeste.vue'
import AT1 from './components/AT1.vue'
import Calculadora from './components/Calculadora.vue'

export default {
  name: 'app',
  data(){

  },
  components: {
    MeuComponente,
    Header,
    ComponenteTeste,
    AT1,
    Calculadora
  }
}

</script>

<style>
.body {
  min-height: 100vh;
  background: rgba(221, 221, 221, 0.459);
}
</style>