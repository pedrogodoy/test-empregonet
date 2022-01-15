<template>
  <q-input class="col-12" outlined v-model="text" label="Local">
    <template v-slot:append>
      <q-icon name="place" />
    </template>
  </q-input>
</template>

<script>
export default {
  data() {
    return {
      text: ""
    }
  }
}
</script>

<style>

</style>