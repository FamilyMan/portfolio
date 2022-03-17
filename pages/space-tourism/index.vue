<template>
  <div class="main-background">
    <div class="main-grid">
      <div style="grid-area: left">
        <div>
          <h5 :style="$vuetify.breakpoint.md ? 'text-align: center' : ''">So, you want to travel to</h5>
          <h1>Space</h1>
          <div class="text-box-holder">
            <p class="text-box" style="max-width: 492px">
              Let’s face it; if you want to go to space, you might as well genuinely go to
              outer space and not hover kind of on the edge of it. Well sit back, and relax
              because we’ll give you a truly out of this world experience!
            </p>
          </div>
        </div>
      </div>
      <div style="grid-area: right;display: flex;justify-content: center;align-items: center;margin-top: 15vh">
        <nuxt-link style="text-decoration: none" class="explore-button" to="/space-tourism/destination"><h4 style="letter-spacing: 2px;color: black">Explore</h4></nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "space-tourism-index",
  layout: "space-tourism",
}
</script>

<style scoped>
  @import "@/assets/space-tourism.css";

  h4 {
    font-size: 20px;
  }
  .main-background {
    background: linear-gradient(to bottom, rgba(11,13,23,0.25) 100%,rgba(11,13,23,0.25) 100%), url(/portfolio/home/background-home-mobile.jpg) no-repeat center center;
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: cover;
    min-height: 100vh;
  }
  .main-grid {
    grid-template-areas:
    "."
    "left"
    "right";
    grid-template-rows: 13vh 35vh auto;
  }
  .explore-button {
    cursor: default;
    border-radius: 50%;
    background-color: var(--white);
    width: 150px;
    aspect-ratio: 1;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .explore-button:hover {
    transition: 0.3s;
    box-shadow: 0 0 0 50px rgba(255, 255, 255, 0.1);
  }
  @media (min-width: 768px) {
    h4 {
      font-size: 32px;
    }
    .explore-button {
      width: 242px;
    }
    .explore-button:hover {
      box-shadow: 0 0 0 80px rgba(255, 255, 255, 0.1);
    }
  }
  @media (min-width: 960px) {
    .main-background {
      background: linear-gradient(to bottom, rgba(11,13,23,0.25) 100%,rgba(11,13,23,0.25) 100%), url(/portfolio/home/background-home-desktop.jpg) no-repeat center center;
      -webkit-background-size: cover;
      -moz-background-size: cover;
      -o-background-size: cover;
      background-size: cover;
      min-height: 100vh;
    }
    .main-grid {
      grid-template-areas:
        "blank blank"
        "left right";
      grid-template-rows: 41vh auto;
      grid-template-columns: 50% 50%;
    }
    .explore-button {
      width: 274px;
    }
    .explore-button:hover {
      box-shadow: 0 0 0 88px rgba(255, 255, 255, 0.1);
    }
  }
</style>
