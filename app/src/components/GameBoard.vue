<template>
  <div
    class="[&>div:last-child>div]:border-b-0 [&>div>div:last-child]:border-r-0"
  >
    <GameRow
      v-for="(row, i) of board"
      :key="i"
      :row="row"
      @location="fillBoard(i, $event)"
    ></GameRow>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from "vue";
// types
import type { Board, Cell } from "@/types";
// components
import GameRow from "./GameRow.vue";

const defaultBoard = (): Board => {
  return [
    [null, null, null],
    [null, null, null],
    [null, null, null],
  ];
};

const board = ref<Board>([
  [null, null, null],
  [null, null, null],
  [null, null, null],
]);

const turnNumber = ref(1);

const currentMark = computed<Cell>(() => {
  return turnNumber.value % 2 === 0 ? "O" : "X";
});

function reset() {
  board.value = defaultBoard();
  turnNumber.value = 1;
}

function checkWinner(): Cell {
  // Check rows and columns
  for (let i = 0; i < 3; i++) {
    if (
      (board.value[i][0] === board.value[i][1] &&
        board.value[i][1] === board.value[i][2] &&
        board.value[i][0]) ||
      (board.value[0][i] === board.value[1][i] &&
        board.value[1][i] === board.value[2][i] &&
        board.value[0][i])
    ) {
      return currentMark.value;
    }
  }

  // Check diagonals
  if (
    (board.value[0][0] === board.value[1][1] &&
      board.value[1][1] === board.value[2][2] &&
      board.value[0][0]) ||
    (board.value[0][2] === board.value[1][1] &&
      board.value[1][1] === board.value[2][0] &&
      board.value[0][2])
  ) {
    return currentMark.value;
  }

  // No winner yet
  return null;
}

function fillBoard(row: number, col: number) {
  board.value[row][col] = currentMark.value;
  if (checkWinner()) {
    alert(`${currentMark.value} Wins!`);
    reset();
    return;
  }
  // Check for draws
  if (turnNumber.value === 9) {
    alert("Draw!");
    reset();
    return;
  }
  turnNumber.value++;
}
</script>
