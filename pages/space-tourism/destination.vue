<template>
  <div class="main-background">
    <div class="main-grid">
      <div style="grid-area: head">
        <h5><span style="opacity: 0.25;font-weight: bold">01</span> Pick your destination</h5>
      </div>
      <div style="grid-area: left;position: relative;display: flex;justify-content: center">
        <img class="pic" :src="items[tab].image" :alt="`Picture of ${items[tab].title}`">
      </div>
      <div style="grid-area: menu" class="menu" v-if="items">
        <v-tabs
          v-model="tab"
          background-color="transparent"
          dark
        >
          <v-tab
            v-for="item in items"
            :key="item.title"
            style="min-width: 41px"
          >
            <span style="font-family: 'Barlow Condensed', sans-serif;font-size: 16px;letter-spacing: 2.7px;color: var(--white);text-transform: uppercase;font-weight: 400;">{{ item.title }}</span>
          </v-tab>
        </v-tabs>
      </div>
      <div style="grid-area: right">
        <div class="text-box-holder">
          <div style="margin-top: 24px">
            <h2>{{ items[tab].title }}</h2>
            <div class="text-box">
              <p>{{ items[tab].content }}</p>
              <hr style="margin: 54px 0 28px;border: 0;border-top: 1px solid #383B4B">
              <div class="bottom-div">
                <div class="distance-div">
                  <p class="subheading2">Avg. distance</p><h4 class="subheading1">{{ items[tab].distance }}</h4>
                </div>
                <div>
                  <p class="subheading2">Est. travel time</p><h4 class="subheading1">{{ items[tab].travelTime }}</h4>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "destination",
  layout: "space-tourism",
  data() {
    return {
      tab: 0,
      items: [
        { title: 'Moon', image: '/portfolio/destination/image-moon.png', content: 'See our planet as you’ve never seen it before. A perfect relaxing trip away to help regain perspective and come back refreshed. While you’re there, take in some history by visiting the Luna 2 and Apollo 11 landing sites.', distance: "384,400 km", travelTime: "3 days" },
        { title: 'Mars', image: '/portfolio/destination/image-mars.png', content: 'Don’t forget to pack your hiking boots. You’ll need them to tackle Olympus Mons the tallest planetary mountain in our solar system. It’s two and a half times the size of Everest!', distance: "225 mil. km", travelTime: "9 months" },
        { title: 'Europa', image: '/portfolio/destination/image-europa.png', content: 'The smallest of the four Galilean moons orbiting Jupiter, Europa is a winter lover’s dream. With an icy surface, it’s perfect for a bit of ice skating, curling, hockey, or simple relaxation in your snug wintery cabin.', distance: "628 mil. km", travelTime: "3 years" },
        { title: 'Titan', image: '/portfolio/destination/image-titan.png', content: 'The only moon known to have a dense atmosphere other than Earth, Titan is a home away from home (just a few hundred degrees colder!). As a bonus, you get striking views of the Rings of Saturn.', distance: "1.6 bil. km", travelTime: "7 years" }
      ]
    }
  }
}
</script>

<style scoped>
  @import "@/assets/space-tourism.css";

  .distance-div {
    min-width: 221px;
    margin-bottom: 32px;
  }
  .menu {
    margin: 0 auto;
  }
  .main-background {
    background: linear-gradient(to bottom, rgba(11,13,23,0.25) 100%,rgba(11,13,23,0.25) 100%), url(/portfolio/destination/background-destination-mobile.jpg) no-repeat center center;
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: cover;
    min-height: 100vh;
  }
  ::v-deep p {
    margin-bottom: 0;
  }
  .main-grid {
    grid-template-areas:
    "."
    "head"
    "left"
    "menu"
    "right";
    grid-template-rows: 12vh 7vh 26vh 3vh auto;
  }
  @media (min-width: 768px) {
    .distance-div {
      margin-bottom: 0;
    }
    .bottom-div {
      display: flex;
    }
    .main-grid {
      grid-template-rows: 12vh 9vh 34vh 3vh auto;
    }
  }
  @media (min-width: 960px) {
    img.pic {
      width: -webkit-fill-available;
      height: fit-content;
      max-width: fit-content;
    }
    .menu {
      margin: unset;
    }
    .main-background {
      background: linear-gradient(to bottom, rgba(11,13,23,0.25) 100%,rgba(11,13,23,0.25) 100%), url(/portfolio/destination/background-destination-desktop.jpg) no-repeat center center;
      -webkit-background-size: cover;
      -moz-background-size: cover;
      -o-background-size: cover;
      background-size: cover;
      min-height: 100vh;
    }
    .main-grid {
      grid-template-areas:
    ". ."
    "head ."
    ". menu"
    "left right";
      grid-template-rows: 23vh 10vh 5vh auto;
      grid-template-columns: 52% 48%;
    }
  }
</style>
