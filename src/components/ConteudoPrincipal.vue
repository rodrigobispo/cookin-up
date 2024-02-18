<template>
  <main class="conteudo-principal">
    <SuaLista :ingredientes="ingredientes" />
    <SelecionarIngredientes />
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import SelecionarIngredientes from './SelecionarIngredientes.vue';
import SuaLista from './SuaLista.vue';

export default defineComponent({
  components: { SelecionarIngredientes, SuaLista },
  data() {
    return {
      ingredientes: ['Alho', 'Manteiga', 'Leite']
    };
  },
})
</script>
