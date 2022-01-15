<template>
  <q-page class="row q-py-lg" 
    :style="$q.screen.gt.lg ? 'margin: 0 200px 0 200px' : ''" :class="$q.screen.lt.md ? 'q-px-sm' : 'q-px-xl q-mx-xl'">
  
    <div class="row col-xl-5 col-lg-5 col-md-5 col-sm-12 col-xs-12">
      <search-by-role />
    </div>

    <div class="col-12 lt-md q-mt-lg">
     <vacancies-found-on-mobile :jobsCount="jobs.length" />
    </div>
      
    <filters-button-on-mobile />

    <div class="row col-5 gt-sm">
      <search-by-local />
    </div>

    <div class="bg-re row justify-end col-2 gt-sm">
      <search-jobs-button />
    </div>

    <vacancies-found-result />

    <vacancies-header-desktop :jobsCount="jobs.length" />

    <filters-side-bar />

    <jobs-cards-list :jobs="jobs" />

  </q-page>
</template>

<script>
import SearchByRole from 'components/SearchByRole.vue';
import VacanciesFoundOnMobile from 'src/components/VacanciesFoundOnMobile.vue';
import FiltersButtonOnMobile from 'src/components/FiltersButtonOnMobile.vue';
import SearchByLocal from 'src/components/SearchByLocal.vue';
import SearchJobsButton from 'src/components/SearchJobsButton.vue';
import VacanciesFoundResult from 'src/components/VacanciesFoundResult.vue';
import VacanciesHeaderDesktop from 'src/components/VacanciesHeaderDesktop.vue';
import FiltersSideBar from 'components/FiltersSideBar.vue';
import JobsCardsList from 'src/components/JobsCardsList.vue';

export default {
  name: 'PageIndex',
  components: {
    SearchByRole,
    VacanciesFoundOnMobile,
    FiltersButtonOnMobile,
    SearchByLocal,
    SearchJobsButton,
    VacanciesFoundResult,
    VacanciesHeaderDesktop,
    FiltersSideBar,
    JobsCardsList
  },
  data() {
    return {
      pcd: false,
      jobs: [
        { 
          id: 1,
          name: "Auxiliar Administrativo",
          companyLogo: '/carrefour-logo.png',
          companyName: 'Carrefour',
          datePublish: 'hoje',
          description: 'Rio de Janeiro - RJ - 3 Vagas - CLT',
          salaryRange: 'R$ 2.000,00 a R$ 2.500,00',
          workingDay: 'Segunda a Sexta - 09:00 às 17:00',
          isNew: true 
        },
        { 
          id: 2,
          name: "Caixa",
          companyLogo: '/extra-logo.png',
          companyName: 'Extra',
          datePublish: 'hoje',
          description: 'São Paulo - SP - 3 Vagas - CLT',
          salaryRange: 'R$ 1.000,00 a R$ 2.500,00',
          workingDay: 'Segunda a Sexta - 09:00 às 17:00',
          isNew: true 
        },
        { 
          id: 3,
          name: "Auxiliar Administrativo",
          companyLogo: '/carrefour-logo.png',
          companyName: 'Carrefour',
          datePublish: 'hoje',
          description: 'Rio de Janeiro - RJ - 3 Vagas - CLT',
          salaryRange: 'R$ 2.000,00 a R$ 2.500,00',
          workingDay: 'Segunda a Sexta - 09:00 às 17:00',
          isNew: true 
        },
        { 
          id: 4,
          name: "Caixa",
          companyLogo: '/extra-logo.png',
          companyName: 'Extra',
          datePublish: 'hoje',
          description: 'São Paulo - SP - 3 Vagas - CLT',
          salaryRange: 'R$ 1.000,00 a R$ 2.500,00',
          workingDay: 'Segunda a Sexta - 09:00 às 17:00',
          isNew: true 
        },
        { 
          id: 5,
          name: "Auxiliar Administrativo",
          companyLogo: '/carrefour-logo.png',
          companyName: 'Carrefour',
          datePublish: 'hoje',
          description: 'Rio de Janeiro - RJ - 3 Vagas - CLT',
          salaryRange: 'R$ 2.000,00 a R$ 2.500,00',
          workingDay: 'Segunda a Sexta - 09:00 às 17:00',
          isNew: true 
        },
        { 
          id: 6,
          name: "Caixa",
          companyLogo: '/extra-logo.png',
          companyName: 'Extra',
          datePublish: 'hoje',
          description: 'São Paulo - SP - 3 Vagas - CLT',
          salaryRange: 'R$ 1.000,00 a R$ 2.500,00',
          workingDay: 'Segunda a Sexta - 09:00 às 17:00',
          isNew: true 
        },
      ]
    }
  }
}
</script>
