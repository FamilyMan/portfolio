<template>
  <div style="min-height: 100vh;background-color: var(--dark-blue);display: flex;justify-content: center;align-items: center">
    <v-card v-if="slip" elevation="12" style="font-family: Manrope, sans-serif;min-height: 340px;width: 540px;background-color: var(--dark-grayish-blue);border-radius: 15px;text-align: center;padding: 48px 48px 0 48px">
      <h1 style="font-size: 16px;margin-bottom: 20px;color: var(--neon-green)">ADVICE #{{ slip.id }}</h1>
      <q style="font-size: 28px;font-weight: 800;color: var(--light-cyan)">{{ slip.advice }}</q>
      <v-img style="margin: 40px 0" src="pattern-divider.svg"></v-img>
      <button @click="getAdvice" class="randomize-btn" :class="disabled ? 'disabled' : ''">
        <img src="icon-dice.svg" alt="dice icon">
      </button>
    </v-card>
  </div>
</template>

<script>
export default {
  name: "index",
  data() {
    return {
      slip: null,
      disabled: false
    }
  },
  mounted() {
    this.getAdvice()
  },
  methods: {
    getAdvice() {
      if (!this.disabled) {
        fetch('https://api.adviceslip.com/advice')
          .then(response => response.json())
          .then(data => {
            this.disabled = true
            setTimeout(() => {
              this.disabled = false
            }, 2000)
            this.slip = data.slip
          })
          .catch(err => console.error(err))
      }
    }
  }
}
</script>

<style scoped>
::v-deep {
  --light-cyan: hsl(193, 38%, 86%);
  --neon-green: hsl(150, 100%, 66%);
  --grayish-blue: hsl(217, 19%, 38%);
  --dark-grayish-blue: hsl(217, 19%, 24%);
  --dark-blue: hsl(218, 23%, 16%);
}
.randomize-btn {
  background-color: var(--neon-green);
  border: none;
  border-radius: 50% !important;
  cursor: pointer;
  position: absolute;
  bottom: -32px;
  left: calc(50% - 32px);
  height: 64px;
  width: 64px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.randomize-btn:hover {
  box-shadow: 0 0 35px -3px var(--neon-green);
}

.disabled {
  box-shadow: none;
  background-color: var(--grayish-blue);
  cursor: not-allowed;
}

.disabled:hover {
  box-shadow: none;
}
</style>
