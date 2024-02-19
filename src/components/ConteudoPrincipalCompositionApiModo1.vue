<template>
  <main class="conteudo-principal">
    <SuaLista :ingredientes="ingredientes" />
    <SelecionarIngredientes
      @adicionarIngrediente="adicionaIngrediente"
      @removerIngrediente="removeIngrediente" />
  </main>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import SelecionarIngredientes from './SelecionarIngredientes.vue';
import SuaLista from './SuaLista.vue';

export default defineComponent({
  setup() {
    const ingredientes = ref<string[]>([]);

    function adicionaIngrediente(ingrediente: string) {
      ingredientes.value.push(ingrediente);
    }
    function removeIngrediente(ingrediente: string) {
      ingredientes.value = ingredientes.value.filter(ingredienteLista => ingredienteLista !== ingrediente);
    }

    return {
      ingredientes,
      adicionaIngrediente,
      removeIngrediente
    }
  },
  components: { SelecionarIngredientes, SuaLista },
})
</script>
