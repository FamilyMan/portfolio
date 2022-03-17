<template>
  <v-app>
    <nav>
      <SpaceTourismMobileMenuBar v-if="$vuetify.breakpoint.mobile" />
      <SpaceTourismMenuBar v-else />
    </nav>
    <v-main style="min-height: 100vh;background-color: hsl(230, 35%, 7%)" :style="$vuetify.breakpoint.mobile ? 'margin-top: -56px' : 'margin-top: -64px'">
      <Nuxt />
    </v-main>
  </v-app>
</template>

<script>
export default {
}
</script>
