<template>
  <h1>アジェンダ</h1>
  <div class="grid items-center h-4/5">
    <ul>
      <li
        v-for="(agenda, i) in agendas"
        :class="{
          'opacity-90': !step || step === i + 1,
          'opacity-50': step && step !== i + 1,
        }"
      >
        {{ agenda }}
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
defineProps<{
  step?: number;
}>();

const agendas = ref([
  "クラス・抽象クラス・インターフェースについて",
  "現実世界で例えてみる",
  '何故それらが必要なのか',
  '現実的なユースケース',
]);
</script>

<style scoped>
li {
  font-size: 1.8rem !important;
}
</style>
