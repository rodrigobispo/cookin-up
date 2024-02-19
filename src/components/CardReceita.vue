<template>
  <article class="receita">
    <header class="receita__cabecalho">
      <img :src="`/imagens/receitas/${receita.imagem}`" alt="`Foto de ${receita.nome}`" class="receita__imagem">
    </header>

    <section class="receita__corpo">
      <h2 class="paragrafo receita__nome">
        {{ receita.nome }}
      </h2>
    </section>
  </article>
</template>

<script lang="ts">
import { defineComponent, type PropType } from 'vue';
import Tag from './Tag.vue';
import IngredienteSelecionavel from './IngredienteSelecionavel.vue';
import type IReceita from '@/interfaces/IReceita';

export default defineComponent({
  name: 'CardReceita',
  props: {
    receita: {
      type: Object as PropType<IReceita>,
      required: true
    }
  },
  emits: ['adicionarIngrediente', 'removerIngrediente'],
  components: { Tag, IngredienteSelecionavel },
})
</script>

<style scoped>
.receita {
  display: flex;
  width: 17.625rem;
  max-width: 19.5rem;
  flex-direction: column;
  align-items: center;

  border-radius: 1rem;
  background: var(--Branco, #FFF);
  box-shadow: 4px 4px 12px 0px rgba(68, 68, 68, 0.08);
}

.receita__cabecalho {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
}

.receita__corpo {
  padding: 2rem 1rem;
}

.receita__imagem {
  width: 100%;
  border-radius: 1rem 1rem 0rem 0rem;
  display: block;
}

.receita__nome {
  font-weight: 700;
  color: var(--cinza, #444);
}
</style>
