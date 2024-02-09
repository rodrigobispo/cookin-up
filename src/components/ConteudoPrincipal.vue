<template>
  <main class="conteudo-principal">
    <section>
      <span class="substituto-lg sua-lista-texto">
        Sua lista:
      </span>

      <ul class="ingredientes-sua-lista">
        <li v-for="ingrediente in ingredientes" class="ingrediente">
          {{ ingrediente }}
        </li>
      </ul>
    </section>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return {
      ingredientes: ['Alho', 'Manteiga', 'Leite']
    }
  }
})
</script>
