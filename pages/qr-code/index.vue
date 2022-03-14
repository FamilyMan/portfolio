<template>
  <div style="min-height: 100vh;background-color: var(--light-gray);display: flex;justify-content: center;align-items: center">
    <v-card elevation="12" style="font-family: Outfit, sans-serif;max-width: 320px;background-color: var(--white);border-radius: 20px;text-align: center">
      <v-img src="image-qr-code.png" style="border-radius: 10px;margin: 16px 16px 20px"></v-img>
      <h1 style="font-size: 22px;line-height: 28px;margin: 0 16px 16px;font-weight: 700">Improve your front-end skills by building projects</h1>
      <p style="margin: 0 32px 40px;font-size: 15px;line-height: 19px;font-weight: 400;color: var(--grayish-blue)">Scan the QR code to visit Frontend Mentor and take your coding skills to the next level</p>
    </v-card>
  </div>
</template>
<style scoped>
::v-deep {
  --white: hsl(0, 0%, 100%);
  --light-gray: hsl(212, 45%, 89%);
  --grayish-blue: hsl(220, 15%, 55%);
  --dark-blue: hsl(218, 44%, 22%);
}
</style>
