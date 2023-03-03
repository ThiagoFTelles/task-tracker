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
            v-model="descricao"
            type="text"
            class="input"
            placeholder="Nova Tarefa"
          >
        </label>
      </div>
      <div class="column">
        <TemporizadorFormulario @ao-temporizador-finalizado="finalizarTarefa"/>
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
  data() {
    return {
      descricao: '',
    };
  },
  methods: {
    finalizarTarefa(tempoDecorrido: number) : void {
      console.log(tempoDecorrido, this.descricao);
      this.descricao = '';
    },
  },
});
</script>

<style scoped>
</style>
