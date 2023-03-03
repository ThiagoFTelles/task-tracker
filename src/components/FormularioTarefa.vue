<template>
  <div class="box">
    <div class="columns">
      <div
        class="column is-8"
        role="form"
        aria-label="Formulário para criação de uma nova tarefa."
      >
        <label for="input-tarefa">
          Nova Tarefa
          <input
            id="input-tarefa"
            type="text"
            class="input"
            placeholder="Nova Tarefa"
          >
        </label>
      </div>
      <div class="column">
        <TemporizadorFormulario />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import TemporizadorFormulario from './TemporizadorFormulario.vue';

export default defineComponent({
  name: 'FormularioTarefa',
  components: { TemporizadorFormulario },
});
</script>

<style scoped>
</style>
