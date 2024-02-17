<template>
  <main class="conteudo-principal">
    <section>
      <span class="substituto-lg sua-lista-texto">
        Sua lista:
      </span>

      <ul v-if="ingredientes.length" class="ingredientes-sua-lista">
        <li v-for="ingrediente in ingredientes" :key="ingrediente">
          <Tag :texto="ingrediente" ativa />
        </li>
      </ul>
      <p v-else class="paragrafo lista-vazia">
        <img src="../assets/images/icones/lista-vazia.svg" alt="Ícone de pesquisa">
        Sua lista está vazia. Selecione ingredientes para iniciar.
      </p>
    </section>

    <SelecionarIngredientes />
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import SelecionarIngredientes from './SelecionarIngredientes.vue';
import Tag from './Tag.vue';

export default defineComponent({
  components: { SelecionarIngredientes, Tag },
  data() {
      return {
          ingredientes: ['Alho', 'Manteiga', 'Leite']
      };
  },
})
</script>
