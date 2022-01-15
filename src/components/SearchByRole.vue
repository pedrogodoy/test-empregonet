<template>
  <q-input class="col-xl-11 col-lg-11 col-md-11 col-sm-12 col-xs-12" outlined v-model="text" label="Cargo">
    <template v-slot:append>
      <q-icon name="search" />
    </template>
  </q-input>
</template>

<script>
export default {
  data() {
    return {
      text: "",
    }
  }
}
</script>

<style>

</style>