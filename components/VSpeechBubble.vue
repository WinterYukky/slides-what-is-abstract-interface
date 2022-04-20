<template>
  <div class="v-speech-bubble relative bg-blue-400 border border-blue-500 p-4 rounded-xl">
    <slot></slot>
  </div>
</template>

<style scoped>

.v-speech-bubble::before {
  content: "";
  clip-path: polygon(0 50%, 100% 0, 100% 100%);
  width: 8px;
  height: 12px;
  transform: translate(-9px, -50%);
  @apply absolute top-1/2 left-0 bg-blue-500;
}

.v-speech-bubble::after {
  content: "";
  clip-path: polygon(0 50%, 100% 0, 100% 100%);
  width: 8px;
  height: 12px;
  transform: translate(-8px, -50%);
  @apply absolute top-1/2 left-0 bg-blue-400;
}
</style>