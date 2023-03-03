<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <BarraLateral />
    </div>
    <div class="column is-trhee-quarter">
      <FormularioTarefa />
      <div class="lista">
        <detalhes-tarefa />
        <detalhes-tarefa />
        <detalhes-tarefa />
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import BarraLateral from './components/BarraLateral.vue'
import FormularioTarefa from './components/FormularioTarefa.vue'
import DetalhesTarefa from './components/lista-de-tarefas/DetalhesTarefa.vue'

export default defineComponent({
  name: 'App',
  components: { BarraLateral, FormularioTarefa, DetalhesTarefa },
})
</script>

<style>
.lista {
  padding: 1.25rem;
}
</style>
