<template>
    <div class="inline-flex flex-col sm:flex-row items-center border-2 border-gray-300 p-4 rounded-lg shadow-lg bg-white mx-auto">
      <!-- Первая буква первого слова в квадрате -->
      <div class="flex items-center justify-center bg-black text-white w-14 h-14 text-3xl font-bold rounded-full mb-4 sm:mb-0 sm:mr-2">
        <slot name="first-letter-1" />
      </div>
      <!-- Остальная часть первого слова -->
      <h1 class="text-3xl sm:text-4xl font-bold text-gray-900 tracking-wide">
        <slot name="first-word" />
      </h1>
      <!-- Первая буква второго слова в квадрате -->
      <div class="flex items-center justify-center bg-black text-white w-14 h-14 text-3xl font-bold rounded-full mt-4 sm:mt-0 sm:ml-4 sm:mr-2">
        <slot name="first-letter-2" />
      </div>
      <!-- Остальная часть второго слова -->
      <h1 class="text-3xl sm:text-4xl font-bold text-gray-900 tracking-wide">
        <slot name="second-word" />
      </h1>
      <!-- Дополнительный контент -->
      <div class="mt-4 sm:ml-4">
        <slot name="additional-content" />
      </div>
    </div>
  </template>
  
  <script setup>
  </script>
  