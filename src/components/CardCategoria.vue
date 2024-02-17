<template>
  {{ categoria.nome }} {{ categoria.imagem }}
</template>

<script lang="ts">
import type ICategoria from '@/interfaces/ICategoria';
import { defineComponent, type PropType } from 'vue';

export default defineComponent({
  name: 'CardCategoria',
  props: {
    categoria: {
      type: Object as PropType<ICategoria>,
      required: true
    }
  }
})
</script>