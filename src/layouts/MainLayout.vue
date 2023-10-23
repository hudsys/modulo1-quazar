<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="flex justify-between items-center q-pa-md">
        <q-icon name="keyboard_arrow_left" size="25px"></q-icon>
        <q-toolbar-title class="text-center">GEAF-WEB</q-toolbar-title>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = !leftDrawerOpen"
        />        
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-1"
    >
      <q-list>
        <q-item-label header class="text-grey-8">
          Menu Principal
        </q-item-label>
        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue'

const linksData = [
  {
    title: 'Início',
    caption: 'Início da Aplicação',
    icon: 'school',
    link: 'http://www.geaf-web.com.br:9010/'
  },
  {
    title: 'Cursos',
    caption: 'Ir para Site de Cursos',
    icon: 'code',
    link: 'http://www.geaf-web.com.br:9020/'
  }
]

export default {
  name: 'MainLayout',
  components: {
    EssentialLink
  },
  data () {
    return {
      leftDrawerOpen: false,
      essentialLinks: linksData
    }
  }
}
</script>


<style lang="stylus">
  .header { 
    background-color: #e067b8;
  }
  .q-page-container {
    padding-top : 65px !important;
  }
</style>