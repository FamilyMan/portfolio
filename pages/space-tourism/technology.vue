<template>
  <div class="main-background">
    <div class="main-grid">
      <div style="grid-area: head">
        <h5><span style="color: #ffffff;opacity: 0.25">03</span> Space launch 101</h5>
      </div>
      <div style="grid-area: left">
        <div style="grid-area: right" v-if="items">
          <div class="buttons">
            <v-btn-toggle mandatory v-model="tab" style="background-color: transparent">
              <v-btn v-for="(item, index) in items" :key="item.title" text height="112">
                <div class="circle"><h4 :style="tab === index ? 'color: black' : 'color: white'">{{ index + 1}}</h4></div>
              </v-btn>
            </v-btn-toggle>
          </div>
        </div>
        <div class="content-box">
          <h6>The terminology...</h6>
          <h3>{{ items[tab].title }}</h3>
          <div class="text-box-holder">
            <p class="text-box">{{ items[tab].content }}</p>
          </div>
        </div>
      </div>
      <div style="grid-area: right;display: flex;justify-content: end;align-items: center">
        <img :srcset="items[tab].srcset" sizes="(max-width: 960px) 768px, 515px" :src="items[tab].image" :alt="`Picture of ${items[tab].title}`">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "technology",
  layout: "space-tourism",
  data() {
    return {
      tab: 0,
      items: [
        {
          title: 'Launch vehicle',
          srcset: '/portfolio/technology/image-launch-vehicle-landscape.jpg 768w, /portfolio/technology/image-launch-vehicle-portrait.jpg, 515w',
          image: '/portfolio/technology/image-launch-vehicle-landscape.jpg',
          content: 'A launch vehicle or carrier rocket is a rocket-propelled vehicle used to carry a payload from Earth\'s surface to space, usually to Earth orbit or beyond. Our WEB-X carrier rocket is the most powerful in operation. Standing 150 metres tall, it\'s quite an awe-inspiring sight on the launch pad!'
        },
        {
          title: 'Spaceport',
          srcset: '/portfolio/technology/image-spaceport-landscape.jpg 768w, /portfolio/technology/image-spaceport-portrait.jpg, 515w',
          image: '/portfolio/portfolio/technology/image-spaceport-portrait.jpg',
          content: 'A spaceport or cosmodrome is a site for launching (or receiving) spacecraft, by analogy to the seaport for ships or airport for aircraft. Based in the famous Cape Canaveral, our spaceport is ideally situated to take advantage of the Earth’s rotation for launch.'
        },
        {
          title: 'Space capsule',
          srcset: '/portfolio/technology/image-space-capsule-landscape.jpg 768w, /portfolio/technology/image-space-capsule-portrait.jpg, 515w',
          image: '/portfolio/portfolio/technology/image-space-capsule-portrait.jpg',
          content: 'A space capsule is an often-crewed spacecraft that uses a blunt-body reentry capsule to reenter the Earth\'s atmosphere without wings. Our capsule is where you\'ll spend your time during the flight. It includes a space gym, cinema, and plenty of other activities to keep you entertained.'
        }
      ]
    }
  }
}
</script>

<style scoped>
  @import "@/assets/space-tourism.css";

  h6 {
    font-family: "Barlow Condensed", sans-serif;
    color: var(--light-violet);
    font-weight: 400;
    text-transform: uppercase;
    font-size: 16px;
    letter-spacing: 2.7px;
  }
  img {
    width: 100%;
  }
  .main-background {
    background: linear-gradient(to bottom, rgba(11,13,23,0.25) 100%,rgba(11,13,23,0.25) 100%), url(/portfolio/technology/background-technology-mobile.jpg) no-repeat center center;
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
    "left";
    grid-template-rows: 12vh 7vh 26vh auto;
  }
  .circle {
    border-radius: 50%;
    border: 1px solid rgba(255, 255, 255, 0.25);
    width: 40px;
    height: 40px;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  ::v-deep .v-btn--active .circle {
    opacity: 1;
    background-color: white;
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
    "right"
    "left";
      grid-template-rows: 12vh 9vh 37vh auto;
    }
    .circle {
      width: 60px;
      height: 60px;
    }
  }
  @media (min-width: 960px) {
    img {
      object-fit: contain;
    }
    .content-box {
      margin-left: 160px;
    }
    .circle {
      width: 80px;
      height: 80px;
    }
    .main-background {
      background: linear-gradient(to bottom, rgba(11,13,23,0.25) 100%,rgba(11,13,23,0.25) 100%), url(/portfolio/technology/background-technology-desktop.jpg) no-repeat center center;
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
        "left right";
      grid-template-rows: 23vh 17vh auto;
      grid-template-columns: minmax(635px, 55%) auto;
    }
    .buttons {
      float: left;
    }
    ::v-deep .v-item-group {
      flex-direction: column;
    }
  }
</style>
