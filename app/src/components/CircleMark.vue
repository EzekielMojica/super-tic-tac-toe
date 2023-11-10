<template>
  <svg
    viewBox="0 0 100 100"
    xmlns="http://www.w3.org/2000/svg"
    width="100%"
    height="100%"
  >
    <circle
      cx="50"
      cy="50"
      r="40"
      fill="none"
      stroke="black"
      stroke-width="2"
      stroke-dasharray="251.327"
      stroke-dashoffset="251.327"
      style="opacity: 0"
    >
      <animate
        attributeName="opacity"
        values="0; 1"
        dur="0.25s"
        begin="0s"
        fill="freeze"
      />
      <animate
        attributeName="stroke-dashoffset"
        values="251.327; 0"
        dur="0.5s"
        begin="0.25s"
        fill="freeze"
      />
    </circle>
  </svg>
</template>
