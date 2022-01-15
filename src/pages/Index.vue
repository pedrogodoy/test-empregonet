<template>
  <q-page class="row q-py-lg" :class="$q.screen.lt.md ? 'q-px-sm' : 'q-px-xl q-mx-xl'">
  
    <div class="row col-xl-5 col-lg-5 col-md-5 col-sm-12 col-xs-12">
      <q-input class="col-xl-11 col-lg-11 col-md-11 col-sm-12 col-xs-12" outlined v-model="text" label="Cargo">
        <template v-slot:append>
          <q-icon name="search" />
        </template>
      </q-input>
    </div>

    <div class="col-12 lt-md q-mt-lg">
      <div class="text-small text-grey">
        450 vagas encontradas
      </div>
    </div>
      
    <div class="row col-12 lt-md q-mt-lg justify-between">
      <q-btn outline class="col-2" no-caps>
        <q-icon name="fas fa-sliders-h" size="15px" />
      </q-btn>

      <q-btn outline class="col-6" no-caps>
        Rio de janeiro - 5 km
      </q-btn>

      <q-btn outline class="col-3" no-caps>
        tipo
      </q-btn>
    </div>


    <div class="row col-5 gt-sm">
      <q-input class="col-12" outlined v-model="text" label="Local">
        <template v-slot:append>
          <q-icon name="place" />
        </template>
      </q-input>
    </div>

    <div class="bg-re row justify-end col-2 gt-sm">
      <q-btn class="col-10" outline color="black" no-caps>
          Buscar vagas
      </q-btn>
    </div>

    <div class="col-12 bg-blu">
      <div class="col-6">
        <h5>Vagas de emprego para Auxiliar Administrativo em Santo amaro - São Paulo - SP</h5>
      </div>
    </div>

    <div class="row justify-between col-12 gt-sm">
      <div class="text-h5">
        Filtros
      </div>
      <div class="text-h5 q-mr-xl">
        23 vagas encontradas
      </div>
      <q-toggle
        v-model="pcd"
        label="Exclusiva para PCD"
        left-label
      />
    </div>

    <div class="col-3 gt-sm">
      <span class="text-h6 bg-blu">Distância</span>
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

      <span class="text-h6">Tipo de vaga</span>
      <q-option-group
        :options="vacanciesTypes"
        type="radio"
        v-model="vacanciesType"
      />
      
      <q-separator class="q-mb-lg" />

      <span class="text-h6">Tipo de cargo</span>
      <q-option-group
        :options="contractTypes"
        type="checkbox"
        v-model="contractType"
      />
      
      <q-separator class="q-mb-lg" />

      <span class="text-h6">Faixa salarial</span>
      <q-option-group
        :options="salariesRange"
        type="checkbox"
        v-model="salaryRange"
      />
      
      <q-separator class="q-mb-lg" />

      <span class="text-h6">Experiência no cargo</span>
      <q-option-group
        :options="experiences"
        type="checkbox"
        v-model="experience"
      />
      
      <q-separator class="q-mb-lg" />

      <span class="text-h6">Softwares de escritório</span>
      <q-option-group
        :options="officeSoftwares"
        type="checkbox"
        v-model="officeSoftware"
      />
      
      <q-separator class="q-mb-lg" />

      <span class="text-h6">Escolaridade mínima</span>
      <q-option-group
        :options="schoolingOptions"
        type="checkbox"
        v-model="schooling"
      />
      
      <q-separator class="q-mb-lg" />


      <span class="text-h6">Idiomas</span>
      <q-option-group
        :options="languagesOptions"
        type="checkbox"
        v-model="languages"
      />
      
    </div>

    <div class="offset-xl-1 offset-lg-1 offset-md-1 offset-sm-0 offset-xs-0 col-xl-8 col-lg-8 col-md-8 col-sm-12 col-xs-12">
      <q-card v-for="item in 5" :key="item" flat bordered class="q-mb-md">
        <q-card-section class="row justify-between">
          <div class="text-h6">Auxiliar Administrativo</div>
          <q-btn outline round class="gt-sm">
            <q-icon size="15px" name="far fa-star" />
          </q-btn>
          <q-btn class="row items-center lt-md" color="grey" flat no-caps>
            <q-icon size="15px" name="far fa-star" />
            <span class="q-ml-sm">Salvar</span>
          </q-btn>

          <div class="row col-12 items-end">
            <q-avatar>  
              <q-img  width="" src="/carrefour-logo.png" />
            </q-avatar>
            <p>Carrefour</p>
          </div>

          <div class="row col-12">
            <small class="text-grey">Vaga publicada hoje</small>
            <small class="text-primary q-ml-xs">- Nova</small>
          </div>
        </q-card-section>

        <q-separator inset />

        <q-card-section class="q-pt-none row bgblue items-center ustify-center">
          <div class="text-small q-mt-md">Rio de Janeiro - RJ - 3 Vagas - CLT</div>
        </q-card-section>

        <q-separator inset />

        <q-card-section class="row">
          <div class="col-12 text-bold">
            Salário
          </div>
          <div class="col-12">
            R$ 2.000,00 a R$ 2.500,00
          </div>

          <div class="col-12 q-mt-md text-bold">
            Jornada de trabalho
          </div>
          <div class="col-12">
            Segunda a Sexta - 09:00 às 17:00
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

  </q-page>
</template>

<script>
export default {
  name: 'PageIndex',
  data() {
    return {
      text: "",
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
      pcd: false

    }
  }
}
</script>
