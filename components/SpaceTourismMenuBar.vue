<template>
  <v-app-bar flat class="menu-bar" color="transparent" absolute>
    <nuxt-link style="margin: auto 0" to="/space-tourism">
      <img class="logo" src="shared/logo.svg" alt="">
    </nuxt-link>
    <v-divider style="background: #ffffff;opacity: 0.25"></v-divider>
    <div class="blurred">
      <v-tabs
        v-model="tab"
        background-color="transparent"
        dark
        height="96"
      >
        <v-tab
          exact
          v-for="(item, index) in items"
          :key="item.text"
          class="navText"
          :to="item.to"
        >
          <span :style="$vuetify.breakpoint.mdAndDown ? 'display: none' : ''" style="font-weight: bold">{{ index.toString().padStart(2, "0")}}</span>&nbsp;{{ item.text }}
        </v-tab>
      </v-tabs>
    </div>
  </v-app-bar>
</template>

<script>
export default {
  name: "SpaceTourismMenubar",
  data() {
    return {
      tab: null,
      items: [
        { text: "Home", to: "/space-tourism" },
        { text: "Destination", to: "/space-tourism/destination" },
        { text: "Crew", to: "/space-tourism/crew" },
        { text: "Technology", to: "/space-tourism/technology" }
      ]
    }
  }
}
</script>

<style scoped>
::v-deep .v-toolbar__content {
  height: 100% !important;
  width: 100%;
  padding: 0;
}
  .logo {
    width: 48px;
    height: 48px;
    margin: 0 auto 0 48px;
  }
  .menu-bar {
    top: 0;
    display: flex;
    align-items: center;
    height: 96px !important;
    width: 100%;
  }
  .blurred {
    display: flex;
    align-items: center;
    height: 100%;
    padding: 0 46px 0 48px;
    background: rgba(255, 255, 255, 0.04);
    backdrop-filter: blur(81.5485px);
  }
  .navText {
    font-family: "Barlow Condensed", sans-serif;
    font-size: 16px;
    letter-spacing: 2.7px;
    color: #ffffff;
    text-transform: uppercase;
    margin-right: 16px;
    text-decoration: none;
  }
@media (min-width: 960px) {
  .menu-bar {
    top: 40px !important;
  }
  .blurred {
    padding: 0 133px 0 123px;
  }
  .logo {
    margin: 0 64px 0 55px;
  }
}
</style>
