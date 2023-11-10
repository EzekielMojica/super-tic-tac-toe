<template>
  <svg
    viewBox="0 0 100 100"
    xmlns="http://www.w3.org/2000/svg"
    width="100%"
    height="100%"
  >
    <line
      x1="10"
      y1="10"
      x2="10"
      y2="10"
      stroke="black"
      stroke-width="2"
      stroke-linecap="round"
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
        attributeName="x2"
        values="10; 90"
        dur="0.5s"
        begin="0.25s"
        fill="freeze"
      />
      <animate
        attributeName="y2"
        values="10; 90"
        dur="0.5s"
        begin="0.25s"
        fill="freeze"
      />
    </line>

    <line
      x1="90"
      y1="10"
      x2="90"
      y2="10"
      stroke="black"
      stroke-width="2"
      stroke-linecap="round"
      style="opacity: 0"
    >
      <animate
        attributeName="opacity"
        values="0; 1"
        dur="0.25s"
        begin="0.5s"
        fill="freeze"
      />
      <animate
        attributeName="x2"
        values="90; 10"
        dur="0.5s"
        begin="0.5s"
        fill="freeze"
      />
      <animate
        attributeName="y2"
        values="10; 90"
        dur="0.5s"
        begin="0.5s"
        fill="freeze"
      />
    </line>
  </svg>
</template>
