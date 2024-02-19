<template>
  <button @click="aoClicar" style="cursor: pointer;">
    <Tag :texto="ingrediente" :ativa="selecionado" />
  </button>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Tag from './Tag.vue';

export default defineComponent({
    name: 'IngredienteSelecionavel',
    props: {
        ingrediente: { type: String, required: true }
    },
    data() {
      return {
        selecionado: false
      }
    },
    methods: {
      aoClicar() {
        this.selecionado = !this.selecionado;
        if (this.selecionado) {
          this.$emit('adicionarIngrediente', this.ingrediente);
        } else {
          this.$emit('removerIngrediente', this.ingrediente);
        }
      }
    },
    emits: ['adicionarIngrediente', 'removerIngrediente'],
    components: { Tag }
})
</script>
