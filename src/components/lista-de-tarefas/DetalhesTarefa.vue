<template>
  <Box>
    <div class="columns">
      <div class="column is-7">
        {{ tarefa.descricao || 'Tarefa sem descrição'}}
      </div>
      <div class="column">
        <CronometroFormulario :tempo-em-segundos="tarefa.duracaoEmSegundos"/>
      </div>
    </div>
  </Box>
</template>

<script lang="ts">
import ITarefa from '@/interfaces/ITarefas'
import { defineComponent, PropType } from 'vue'
import CronometroFormulario from '../CronometroFormulario.vue'
import Box from './BoxTarefa.vue'

export default defineComponent({
  name: 'DetalhesTarefa',
  components: { CronometroFormulario, Box },
  props: {
    tarefa: {
      type: Object as PropType<ITarefa>,
      required: true,
    },
  },
})
</script>

<style scoped>
</style>
