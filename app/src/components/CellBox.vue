<template>
  <div class="border-black h-60 w-60 border-r-2 border-b-2" @click="mark()">
    <CrossMark v-if="cell === 'X'"></CrossMark>
    <CircleMark v-if="cell === 'O'"></CircleMark>
  </div>
</template>

<script setup lang="ts">
import CrossMark from "./CrossMark.vue";
import CircleMark from "./CircleMark.vue";
import type { Cell } from "@/types";

const props = defineProps<{
  cell: Cell;
}>();

const emit = defineEmits<{
  (e: "mark"): void;
}>();

function mark() {
  if (!props.cell) {
    emit("mark");
  }
}
</script>
