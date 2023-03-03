<template>
  <div class="box formulario">
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
import { defineComponent } from 'vue'
import TemporizadorFormulario from './TemporizadorFormulario.vue'

export default defineComponent({
  name: 'FormularioTarefa',
  emits: ['aosalvarTarefa'],
  components: { TemporizadorFormulario },
  data() {
    return {
      descricao: '',
    }
  },
  methods: {
    finalizarTarefa(tempoDecorrido: number) : void {
      this.$emit('aosalvarTarefa', {
        duracaoEmSegundos: tempoDecorrido,
        descricao: this.descricao,
      })
      this.descricao = ''
    },
  },
})
</script>

<style>
.formulario {
  color: var(--texto-primario);
  background-color: var(--bg-primario);
}
</style>
