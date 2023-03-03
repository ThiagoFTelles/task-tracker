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
        <div class="is-flex is-align-items-center is-justify-content-space-between">
          <CronometroFormulario :tempo-em-segundos="tempoEmSegundos" />
          <button class="button" @click="iniciarContagem">
            <span class="icon">
              <i class="fas fa-play"></i>
            </span>
            <span>play</span>
          </button>
          <button class="button" @click="finalizarContagem">
            <span class="icon">
              <i class="fas fa-stop"></i>
            </span>
            <span>stop</span>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import CronometroFormulario from './CronometroFormulario.vue';

export default defineComponent({
  name: 'FormularioTarefa',
  components: { CronometroFormulario },
  data() {
    return {
      tempoEmSegundos: 0,
      cronometro: 0,
    };
  },
  methods: {
    iniciarContagem(): void {
      this.cronometro = setInterval(() => { this.tempoEmSegundos += 1; }, 1000);
    },
    finalizarContagem(): void {
      clearInterval(this.cronometro);
      this.tempoEmSegundos = 0;
    },
  },
});
</script>

<style scoped>
</style>
