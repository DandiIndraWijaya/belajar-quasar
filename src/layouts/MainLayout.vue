<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="header" elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = !leftDrawerOpen"
        />

        <q-toolbar-title>
          Me |>
        </q-toolbar-title>

        <a class="link" href="https://dandiindrawijaya.web.app">> Dandi</a>
      </q-toolbar>
    </q-header>

    <q-drawer
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
          My Apps
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
    title: 'My Deadline',
    caption: 'Note your Deadline',
    icon: 'note',
    link: 'https://mydeadline.web.app'
  },
  {
    title: 'Movies Info',
    caption: 'Providing Movies Information around the world',
    icon: 'movie',
    link: 'https://movies-info-96656.web.app/'
  },
  {
    title: 'Top Euro League',
    caption: 'providing European Football Club Informarion',
    icon: 'play',
    link: 'https://top-euro-league.web.app/'
  }
]

export default {
  name: 'MainLayout',
  components: { EssentialLink },
  data () {
    return {
      leftDrawerOpen: false,
      essentialLinks: linksData
    }
  }
}
</script>

<style>
  .header{
    background-color: black;
  }

  .link{
    text-decoration: unset;
    color: white;
    font-weight: bold;
  }
</style>
