<template>
  <main class="conteudo-principal">
    <SuaLista :ingredientes="ingredientes" />
    <SelecionarIngredientes
      @adicionarIngrediente="adicionaIngrediente"
      @removerIngrediente="removeIngrediente" />
  </main>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import SelecionarIngredientes from './SelecionarIngredientes.vue';
import SuaLista from './SuaLista.vue';

const ingredientes = ref<string[]>([]);

function adicionaIngrediente(ingrediente: string) {
  ingredientes.value.push(ingrediente);
}
function removeIngrediente(ingrediente: string) {
  ingredientes.value = ingredientes.value.filter(ingredienteLista => ingredienteLista !== ingrediente);
}
</script>
