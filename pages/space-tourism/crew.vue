<template>
  <div class="main-background">
    <div class="main-grid">
      <div style="grid-area: head">
        <h5><span style="color: #ffffff;opacity: 0.25">02</span> Meet your crew</h5>
      </div>
      <div style="grid-area: left">
        <div>
          <h4 style="opacity: 0.5">{{ items[tab].title }}</h4>
          <h3>{{ items[tab].name }}</h3>
          <div class="text-box-holder">
            <p class="text-box">{{ items[tab].content }}</p>
          </div>
        </div>
      </div>
      <div style="grid-area: dots" v-if="items">
        <v-btn-toggle mandatory v-model="tab" style="background-color: transparent">
          <v-btn v-for="item in items" :key="item.title" text>
            <div class="circle"></div>
          </v-btn>
        </v-btn-toggle>
      </div>
      <div style="grid-area: right;position: relative;display: flex;justify-content: center">
        <img class="pic" :src="items[tab].image" :alt="`Picture of ${items[tab].name }`">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "crew",
  layout: "space-tourism",
  data() {
    return {
      tab: 0,
      items: [
        { title: 'Commander', name: 'Douglas Hurley', image: '/crew/image-douglas-hurley.png', content: 'Douglas Gerald Hurley is an American engineer, former Marine Corps pilot and former NASA astronaut. He launched into space for the third time as commander of Crew Dragon Demo-2.' },
        { title: 'Mission Specialist', name: 'Mark Shuttleworth', image: '/crew/image-mark-shuttleworth.png', content: 'Mark Richard Shuttleworth is the founder and CEO of Canonical, the company behind the Linux-based Ubuntu operating system. Shuttleworth became the first South African to travel to space as a space tourist.' },
        { title: 'Pilot', name: 'Victor Glover',image: '/crew/image-victor-glover.png',  content: 'Pilot on the first operational flight of the SpaceX Crew Dragon to the International Space Station. Glover is a commander in the U.S. Navy where he pilots an F/A-18.He was a crew member of Expedition 64, and served as a station systems flight engineer.' },
        { title: 'Flight Engineer', name: 'Anousheh Ansari', image: '/crew/image-anousheh-ansari.png', content: 'Anousheh Ansari is an Iranian American engineer and co-founder of Prodea Systems. Ansari was the fourth self-funded space tourist, the first self-funded woman to fly to the ISS, and the first Iranian in space.' }
      ]
    }
  }
}
</script>

<style scoped>
  @import "@/assets/space-tourism.css";

  img.pic {
    height: 100%;
    position: absolute;
    bottom: 0;
    width: -webkit-fill-available;
    max-width: fit-content;
  }
  .main-background {
    background: linear-gradient(to bottom, rgba(11,13,23,0.25) 100%,rgba(11,13,23,0.25) 100%), url(/crew/background-crew-mobile.jpg) no-repeat center center;
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: cover;
    min-height: 100vh;
  }
  .main-grid {
    grid-template-areas:
    "."
    "head"
    "right"
    "dots"
    "left";
    grid-template-rows: 12vh 7vh 32vh 10vh auto;
  }
  .circle {
    border-radius: 50%;
    background-color: white;
    width: 10px;
    height: 10px;
    opacity: 0.17;
  }
  ::v-deep .v-btn--active .circle {
    opacity: 1;
  }
  ::v-deep .theme--light.v-btn--active::before {
    opacity: 0;
  }
  ::v-deep .v-btn-toggle > .v-btn.v-btn {
    border-style: none;
  }
  @media (min-width: 768px) {
    .main-grid {
      grid-template-areas:
      "."
      "head"
      "left"
      "dots"
      "right";
      grid-template-rows: 12vh 8vh 20vh 7vh 53vh;
    }
  }
  @media (min-width: 960px) {
    .circle {
      width: 15px;
      height: 15px;
    }
    img.pic {
      height: unset;
      left: 0;
    }
    .main-background {
      background: linear-gradient(to bottom, rgba(11,13,23,0.25) 100%,rgba(11,13,23,0.25) 100%), url(/crew/background-crew-desktop.jpg) no-repeat center center;
      -webkit-background-size: cover;
      -moz-background-size: cover;
      -o-background-size: cover;
      background-size: cover;
      min-height: 100vh;
    }
    .main-grid {
      grid-template-areas:
        ". ."
        "head right"
        "left right"
        "dots right";
      grid-template-rows: 23vh 21vh 41vh 15vh;
      grid-template-columns: 55% 45%;
    }
  }
</style>
