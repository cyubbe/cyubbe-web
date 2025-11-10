<script setup>
import BaseButton from "@/BaseButton.vue";
import BaseNavbar from "@/BaseNavbar.vue";
</script>

<template>

  <div class="app-container">
    <BaseNavbar />

    <main class="content">
      <h1 class="welcome">Out for the Ancients</h1>
      <BaseButton class="bb" href="https://www.w3schools.com">Start</BaseButton>
    </main>

  </div>

</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Jost:ital,wght@0,100..900;1,100..900&display=swap");

:global(html, body) {
  background-image: url("https://4kwallpapers.com/images/wallpapers/stars-galaxy-3840x2160-10307.jpg");
  background-size: 100%;
  background-repeat: repeat;
  background-position: center;
  margin: 0;
  padding: 0;
  height: 100%;
}

.app-container {
  display: flex;
  min-height: 100vh;
}

.content {
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.welcome {
  font-family: "Jost";
  font-size: 50px;
  color: white;
  text-align: center;
  margin-bottom: 1rem;
}

.bb {
  display: flex;
  justify-content: center;
}
</style>
