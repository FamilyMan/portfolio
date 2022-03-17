<template>
<div>

  <v-app-bar flat color="transparent" absolute>
    <nuxt-link style="display: flex" to="/space-tourism">
      <img class="image" src="shared/logo.svg" alt="">
    </nuxt-link>
    <div style="width: 100%;display: flex;justify-content: right">
      <v-btn text @click="drawer = true">
        <svg fill="white" viewBox="0 0 100 70" width="24" height="21">
          <rect width="100" height="10"></rect>
          <rect y="33" width="100" height="10"></rect>
          <rect y="66" width="100" height="10"></rect>
        </svg>
      </v-btn>

    </div>
  </v-app-bar>

    <v-navigation-drawer
      right
      v-model="drawer"
      absolute
      temporary
      :style="drawer ? 'height: 100%' : 'height: 0'"
      style="background-color: rgba(255, 255, 255, 0.04);backdrop-filter: blur(81.5485px)"
    >
      <v-list
        nav
        dense
      >
        <v-list-item-group
          v-model="group"
        >
          <v-list-item exact :to="item.to" v-for="(item, index) in items" :key="item.text">
            <v-list-item-title class="menu-text"><span style="font-weight: bold">{{ index.toString().padStart(2, "0")}}</span>&nbsp;{{ item.text }}</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
</div>
</template>

<script>
export default {
  name: "SpaceTourismMenubar",
  data() {
    return {
      drawer: false,
      group: null,
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
  .image {
    width: 40px;
    height: 40px;
    margin-left: 24px;
  }
  .menu-text {
    font-family: 'Barlow Condensed';
    font-weight: 400;
    font-size: 16px;
    line-height: 19px;
    letter-spacing: 2.7px;
    color: #FFFFFF;
  }
  @media (min-width: 450px) {
    .image {
      width: 48px;
      height: 48px;
    }
  }
</style>
