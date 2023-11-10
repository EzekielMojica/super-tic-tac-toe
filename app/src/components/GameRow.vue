<template>
  <div class="flex">
    <CellBox
      v-for="(cell, i) of row"
      :key="i"
      :cell="cell"
      @mark="emit('location', i)"
    ></CellBox>
  </div>
</template>

<script setup lang="ts">
import CellBox from "./CellBox.vue";
import type { Row } from "@/types";

defineProps<{
  row: Row;
}>();

const emit = defineEmits<{
  (e: "location", index: number): void;
}>();
</script>
