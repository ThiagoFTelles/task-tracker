<template>
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
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import CronometroFormulario from './CronometroFormulario.vue';

export default defineComponent({
  name: 'TemporizadorFormulario',
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

<style>

</style>
