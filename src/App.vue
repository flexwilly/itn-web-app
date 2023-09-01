<template>
  <v-app>
    <NavBar />
    <v-main>
      <router-view></router-view>
    </v-main>
    <FooterBar />
  </v-app>
</template>

<script>

import NavBar from './components/NavBar.vue'
import FooterBar from './components/FooterBar.vue'
export default {
  name: 'App',

  components: {
    NavBar,
    FooterBar,
  },

  data: () => ({
    //
  }),
}
</script>
