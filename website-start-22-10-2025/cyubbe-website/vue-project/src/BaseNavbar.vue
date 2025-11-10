<script setup>
import { ref } from "vue";

const isOpen = ref(false);
</script>

<template>
  <div>
    <!-- Burger Icon -->
    <button class="burger" @click="isOpen = !isOpen">
      <span></span>
      <span></span>
      <span></span>
    </button>

    <!-- Sidebar -->
    <nav :class="['sidebar', { open: isOpen }]">
      <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">Custom Spells</a></li>
        <li><a href="#">Lore</a></li>
      </ul>
    </nav>
  </div>

</template>

<style scoped>

.burger {
  position: fixed;
  top: 1rem;
  left: 1rem;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  width: 30px;
  height: 22px;
  background: none;
  border: none;
  cursor: pointer;
  z-index: 1001;
}

.burger span {
  display: block;
  height: 4px;
  background: white;
  border-radius: 2px;
  transition: 0.3s;
}

/* Sidebar */
.sidebar {
  position: fixed;
  top: 0;
  left: -250px;
  width: 250px;
  height: 100vh;
  background-color: #111111;
  color: white;
  transition: left 0.3s ease;
  box-shadow: rgba(0, 0, 0, 0.3) 3px 0 8px;
  z-index: 1000;
}

.sidebar.open {
  left: 0;
}

.sidebar ul {
  list-style: none;
  padding: 0;
}

.sidebar li {
  margin-top: 80px;

}

.sidebar a {
  font-family: "Jost", system-ui;
  color: white;
  text-decoration: none;
  font-size: 1.2rem;
  padding: 20px;
}
</style>
