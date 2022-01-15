<template>
  <div class="col-3 q-pa-md">
    <q-scroll-area
      style="height: 90vh;"
    >
      <div class="row justify-center col-12">
        <span class="text-h5 text-center">Filtros</span>
        <q-separator class="q-mb-lg" />
      </div>
      
      <span class="text-subtitle1 text-bold">Distância</span>
      <div class="row q-px-md">
        <q-slider
          v-model="distance"
          :marker-labels="arrayMarkerLabel"
          :min="0"
          :max="4"
        />
      </div>
      <q-toggle
        v-model="remote"
        label="Remoto"
        left-label
      />
      
      <q-separator class="q-mb-lg" />

      <span class="text-subtitle1 text-bold">Tipo de vaga</span>
      <q-option-group
        :options="vacanciesTypes"
        type="radio"
        v-model="vacanciesType"
      />
      
      <q-separator class="q-mb-lg" />

      <span class="text-subtitle1 text-bold">Tipo de cargo</span>
      <q-option-group
        :options="contractTypes"
        type="checkbox"
        v-model="contractType"
      />
      
      <q-separator class="q-mb-lg" />

      <span class="text-subtitle1 text-bold">Faixa salarial</span>
      <q-option-group
        :options="salariesRange"
        type="checkbox"
        v-model="salaryRange"
      />
      
      <q-separator class="q-mb-lg" />

      <span class="text-subtitle1 text-bold">Experiência no cargo</span>
      <q-option-group
        :options="experiences"
        type="checkbox"
        v-model="experience"
      />
      
      <q-separator class="q-mb-lg" />

      <span class="text-subtitle1 text-bold">Softwares de escritório</span>
      <q-option-group
        :options="officeSoftwares"
        type="checkbox"
        v-model="officeSoftware"
      />
      
      <q-separator class="q-mb-lg" />

      <span class="text-subtitle1 text-bold">Escolaridade mínima</span>
      <q-option-group
        :options="schoolingOptions"
        type="checkbox"
        v-model="schooling"
      />
      
      <q-separator class="q-mb-lg" />


      <span class="text-subtitle1 text-bold">Idiomas</span>
      <q-option-group
        :options="languagesOptions"
        type="checkbox"
        v-model="languages"
      />
    </q-scroll-area>
    <div class="row col-12 q-mt-sm">
      <q-btn @click="applyFilters" no-caps color="primary" class="col-12">
        Aplicar
      </q-btn>
    </div>
  </div>

</template>

<script>
export default {
  name: 'EssentialLink',
  data() {
    return {
      distance: 0,
      arrayMarkerLabel: [
        { value: 0, label: '1km' },
        { value: 1, label: '5km' },
        { value: 2, label: '25km' },
        { value: 3, label: '50km' },
        { value: 4, label: '100km' }
      ],
      remote: false,
      vacanciesTypes: [
        { label: "Profissional - CLT, autônomo, etc...", value: "profissional" },
        { label: "Estágio", value: "estagio" },
        { label: "Aprendiz", value: "aprendiz" }
      ],
      vacanciesType: "",
      contractTypes: [
        { label: "CLT", value: "clt" },
        { label: "CLT - Temporário", value: "clt-temp" },
        { label: "Autônomo", value: "autonomo" },
        { label: "Cooperado", value: "cooperado" },
        { label: "Cargo em comissão (Setor público)", value: "publico" }
      ],
      contractType: [],
      salariesRange: [
        { label: "R$ 1.000 a R$ 2.000", value: "1000-2000" },
        { label: "R$ 2.001 a R$ 3.000", value: "2001-3000" },
        { label: "R$ 3.001 a R$ 4.000", value: "3001-4000" },
        { label: "R$ 4.001 a R$ 5.000", value: "4001-5000" },
        { label: "+ de R$ 5.000,00", value: "5000" }
      ],
      salaryRange: [],
      experiences: [
        { label: "Sem experiência", value: "0" },
        { label: "1 a 2 anos", value: "1-2" },
        { label: "2 a 3 anos", value: "2-3" },
        { label: "3 a 4 anos", value: "3-4" },
        { label: "+ de 5 anos", value: "5" }
      ],
      experience: [],
      officeSoftwares: [
        { label: "Word", value: "word" },
        { label: "Excel", value: "excel" },
        { label: "Power point", value: "powerPoint" },
        { label: "Photoshop / Corel Draw", value: "ps/corel" },
      ],
      officeSoftware: [],
      schoolingOptions: [
        { label: "Ensino fundamental", value: "fundamental" },
        { label: "Ensino médio", value: "medio" },
        { label: "Ensino superior", value: "superior" },
        { label: "Mestrado", value: "mestrado" },
        { label: "Doutorado", value: "doutorado" },
      ],
      schooling: [],
      languagesOptions: [
        { label: "Inglês", value: "fundamental" },
        { label: "Espanhol", value: "medio" },
      ],
      languages: [],
    }
  },
  methods: {
    applyFilters() {
      console.log('chamouu!')
      this.$emit('applyFilters');
    }
  }
}
</script>
