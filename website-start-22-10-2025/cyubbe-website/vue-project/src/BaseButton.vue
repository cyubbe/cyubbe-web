<script setup>
const props = defineProps({
  href: {
    type: String,
    required: true
  }
});
</script>

<template>
  <a :href="props.href" class="button" target="_blank" rel="noopener noreferrer">
    <slot></slot>
  </a>
</template>

<style scoped>
.button {
  display: inline-block;
  text-align: center;
  font-family: "Rubik Glitch", system-ui;
  font-weight: 400;
  margin: 25px;
  width: 200px;
  height: 60px;
  font-size: 30px;
  border: none;
  outline: none;
  color: #fff;
  background: #111;
  cursor: pointer;
  position: relative;
  z-index: 0;
  border-radius: 10px;
  line-height: 60px;
  text-decoration: none;
}

/* glowing effect */
.button:before {
  content: '';
  background: linear-gradient(45deg, #ff0000,#ff7300, #fffb00, #48ff00, #00ffd5, #002bff, #7a00ff, #ff00c8, #ff0000);
  position: absolute;
  top: -2px;
  left: -2px;
  background-size: 400%;
  z-index: -1;
  filter: blur(5px);
  width: calc(100% + 4px);
  height: calc(100% + 4px);
  animation: glowing 20s linear infinite;
  opacity: 0;
  transition: opacity .3s ease-in-out;
  border-radius: 10px;
}

.button:hover:before {
  opacity: 1;
}

.button:after {
  z-index: -1;
  content: '';
  position: absolute;
  width: 100%;
  height: 100%;
  background: #111;
  left: 0;
  top: 0;
  border-radius: 10px;
}

@keyframes glowing {
  0% { background-position: 0 0; }
  50% { background-position: 400% 0; }
  100% { background-position: 0 0; }
}
</style>
