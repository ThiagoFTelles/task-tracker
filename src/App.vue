<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <BarraLateral />
    </div>
    <div class="column is-trhee-quarter">
      <FormularioTarefa @aosalvarTarefa="salvarTarefa"/>
      <div class="lista">
        <detalhes-tarefa v-for="(tarefa, index) in tarefas" :key="index" />
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

export default defineComponent({
  name: 'App',
  components: { 
    BarraLateral, 
    FormularioTarefa, 
    DetalhesTarefa, 
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
