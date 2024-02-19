<template>
  <main class="conteudo-principal">
    <SuaLista :ingredientes="ingredientes" />

    <KeepAlive include="SelecionarIngredientes">
      <SelecionarIngredientes v-if="conteudo === 'SelecionarIngredientes'"
        @adicionarIngrediente="adicionaIngrediente"
        @removerIngrediente="removeIngrediente"
        @buscarReceitas="navegarPara('MostrarReceitas')"
      />

      <MostrarReceitas
        v-else-if="conteudo === 'MostrarReceitas'"
        @editarReceitas="navegarPara('SelecionarIngredientes')"
      />
    </KeepAlive>
  </main>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import SelecionarIngredientes from './SelecionarIngredientes.vue';
import SuaLista from './SuaLista.vue';
import MostrarReceitas from './MostrarReceitas.vue';

const ingredientes = ref<string[]>([]);

type Pagina = 'SelecionarIngredientes' | 'MostrarReceitas';
const conteudo = ref('SelecionarIngredientes' as Pagina);

function adicionaIngrediente(ingrediente: string) {
  ingredientes.value.push(ingrediente);
}
function removeIngrediente(ingrediente: string) {
  ingredientes.value = ingredientes.value.filter(ingredienteLista => ingredienteLista !== ingrediente);
}
function navegarPara(paginaDestino: Pagina) {
  conteudo.value = paginaDestino;
}
</script>
