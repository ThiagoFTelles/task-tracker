<template>
  <div class="box has-text-weight-bold">
    <div class="columns">
      <div class="column is-7">
        Descrição da tarefa
      </div>
      <div class="column">
        <CronometroFormulario :tempo-em-segundos="15"/>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import CronometroFormulario from '../CronometroFormulario.vue';

export default defineComponent({
  name: 'DetalhesTarefa',
  components: { CronometroFormulario },
});
</script>

<style scoped>
.box {background: #FAF0CA;}
</style>
