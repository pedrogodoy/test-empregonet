<template>
  <div class="offset-xl-1 offset-lg-1 offset-md-1 offset-sm-0 offset-xs-0 col-xl-8 col-lg-8 col-md-8 col-sm-12 col-xs-12">
    <q-card v-for="job in jobs" :key="job.id" flat bordered class="q-mb-md">
      <q-card-section class="row justify-between">
        <div class="text-h6">{{ job.name }}</div>
        <q-btn outline round class="gt-sm">
          <q-icon size="15px" name="far fa-star" />
        </q-btn>
        <q-btn class="row items-center lt-md" color="grey" flat no-caps>
          <q-icon size="15px" name="far fa-star" />
          <span class="q-ml-sm">Salvar</span>
        </q-btn>

        <div class="row col-12 items-end">
          <q-avatar>  
            <q-img  width="" :src="job.companyLogo" />
          </q-avatar>
          <p>{{ job.companyName }}</p>
        </div>

        <div class="row col-12">
          <small class="text-grey">Vaga publicada {{ job.datePublish }}</small>
          <small v-if="job.isNew" class="text-primary q-ml-xs">- Nova</small>
        </div>
      </q-card-section>

      <q-separator inset />

      <q-card-section class="q-pt-none row bgblue items-center ustify-center">
        <div class="text-small q-mt-md">{{ job.description }}</div>
      </q-card-section>

      <q-separator inset />

      <q-card-section class="row">
        <div class="col-12 text-bold">
          Salário
        </div>
        <div class="col-12">
          {{ job.salaryRange }}
        </div>

        <div class="col-12 q-mt-md text-bold">
          Jornada de trabalho
        </div>
        <div class="col-12">
          {{ job.workingDay }}
        </div>
        <div class="row justify-end col-12">
          <q-btn flat no-caps color="primary">...mais detalhes</q-btn>
        </div>

        <div class="row col-12">
          <q-btn outline no-caps color="primary" class="col-xl-2 col-lg-2 col-md-3 col-sm-12 col-xs-12">Me candidatar</q-btn>
        </div>
      </q-card-section>
    </q-card>
  </div>
</template>

<script>
export default {
  props: {
    jobs: []
  }
}
</script>

<style>

</style>