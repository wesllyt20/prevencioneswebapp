<template>
  <v-app>
    <v-main>
      <viewPrinciapl/>
    </v-main>
  </v-app>

</template>

<script>
import viewPrinciapl from './components/viewPrinciapl.vue'

export default {
  name: 'App',

  components: {
    viewPrinciapl,
  },

  data: () => ({
    //
  }),
}
</script>
