<template>
  <main class="conteudo-principal">
    <SuaLista :ingredientes="ingredientes" />
    <SelecionarIngredientes
      @adicionarIngrediente="adicionaIngrediente"
      @removerIngrediente="removeIngrediente" />
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
      ingredientes: [] as string[]
    };
  },
  methods: {
    adicionaIngrediente(ingrediente: string) {
      this.ingredientes.push(ingrediente);
    },
    removeIngrediente(ingrediente: string) {
      this.ingredientes = this.ingredientes.filter(ingredienteLista => ingredienteLista !== ingrediente);
    }
  }
})
</script>
