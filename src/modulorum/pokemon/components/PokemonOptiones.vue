<template>
  <div>
    <ul>
      <li>Pokemon 1</li>
      <li>Pokemon 2</li>
      <li>Pokemon 3</li>
      <li>Pokemon 4</li>
    </ul>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped>
@import "tailwindcss";

li {
  @apply bg-white shadow-md rounded-lg p-3 my-2 cursor-pointer w-40 text-center hover:bg-gray-100 transition-all;
}
</style>
