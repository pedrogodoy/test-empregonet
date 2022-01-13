<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="bg-white" elevated>
      <q-toolbar class="row q-py-sm">
        <!-- <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = !leftDrawerOpen"
        /> -->

        <!-- <q-toolbar-title class="bg-black">
          <span class="text-subtitle">emprego.net</span>
          
          <span class="q-mx-sm">|</span>

          <span class="text-grey text-subtitle2">Recrutador</span>
        </q-toolbar-title> -->
        <div class="row col-2 items-center justify-start">
          <span class="text-h6 text-primary text-bold">emprego.net</span>
          <span class="q-mx-sm text-grey">|</span>
          <span class="text-subtitle text-grey">Recrutador</span>
        </div>

        <div class="row col-3 items-center justify-start text-black q-ml-md">
          <q-btn no-caps flat>Home</q-btn>
          <q-btn no-caps flat>Ajuda</q-btn>
          <q-btn no-caps flat>Blog</q-btn>
        </div>

        <div class="row col-7 items-center justify-end text-black">
          <q-btn outline class="q-mr-sm" no-caps>
            <q-icon name="fas fa-user-circle" class="q-mr-sm" size="20px" />
            Entrar
          </q-btn>
          <q-btn color="primary" no-caps>Cadastro grátis</q-btn>
          <span class="q-mx-sm text-grey">|</span>
          <q-btn outline color="primary" no-caps class="q-mr-lg">
            Sou Recrutador
            <q-icon name="fas fa-arrow-right" class="q-ml-sm" size="13px" />
          </q-btn>
        </div>
      </q-toolbar>
    </q-header>

    <!-- <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-1"
    >
      <q-list>
        <q-item-label
          header
          class="text-grey-8"
        >
          Essential Links
        </q-item-label>
        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer> -->

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue'

const linksData = [
  {
    title: 'Docs',
    caption: 'quasar.dev',
    icon: 'school',
    link: 'https://quasar.dev'
  },
  {
    title: 'Github',
    caption: 'github.com/quasarframework',
    icon: 'code',
    link: 'https://github.com/quasarframework'
  },
  {
    title: 'Discord Chat Channel',
    caption: 'chat.quasar.dev',
    icon: 'chat',
    link: 'https://chat.quasar.dev'
  },
  {
    title: 'Forum',
    caption: 'forum.quasar.dev',
    icon: 'record_voice_over',
    link: 'https://forum.quasar.dev'
  },
  {
    title: 'Twitter',
    caption: '@quasarframework',
    icon: 'rss_feed',
    link: 'https://twitter.quasar.dev'
  },
  {
    title: 'Facebook',
    caption: '@QuasarFramework',
    icon: 'public',
    link: 'https://facebook.quasar.dev'
  },
  {
    title: 'Quasar Awesome',
    caption: 'Community Quasar projects',
    icon: 'favorite',
    link: 'https://awesome.quasar.dev'
  }
];

export default {
  name: 'MainLayout',
  components: {  },
  data () {
    return {
      leftDrawerOpen: false,
      essentialLinks: linksData
    }
  }
}
</script>
