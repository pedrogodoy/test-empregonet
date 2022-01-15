<template>
  <div class="row justify-between col-12 gt-sm">
    <div class="text-h5">
      Filtros
    </div>
    <div class="text-h5 q-mr-xl">
      {{ jobsCount }} vagas encontradas
    </div>
    <q-toggle
      v-model="pcd"
      label="Exclusiva para PCD"
      left-label
    />
  </div>
</template>

<script>
export default {
  props: {
    jobsCount: {}
  },
  data() {
    return {
      pcd: false
    }
  }
}
</script>

<style>

</style>