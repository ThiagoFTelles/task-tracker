<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <BarraLateral />
    </div>
    <div class="column is-trhee-quarter">
      <FormularioTarefa @aosalvarTarefa="salvarTarefa"/>
      <div class="lista">
        <detalhes-tarefa v-for="(tarefa, index) in tarefas" :key="index" :tarefa="tarefa" />
        <Box   v-if="!tarefas.length">
          <p>Nenhuma tarefa iniciada hoje.</p>
        </Box>
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import BarraLateral from './components/BarraLateral.vue'
import FormularioTarefa from './components/FormularioTarefa.vue'
import DetalhesTarefa from './components/lista-de-tarefas/DetalhesTarefa.vue'
import ITarefa from './interfaces/ITarefas'
import Box from './components/lista-de-tarefas/BoxTarefa.vue'

export default defineComponent({
  name: 'App',
  components: { 
    BarraLateral, 
    FormularioTarefa, 
    DetalhesTarefa, 
    Box,
  },
  data() {
    return {
      tarefas: [] as ITarefa[],
    }
  },
  methods: {
    salvarTarefa(tarefa: ITarefa) {
      this.tarefas.push(tarefa)
    },
  },
})
</script>

<style>
.lista {
  padding: 1.25rem;
}
</style>
