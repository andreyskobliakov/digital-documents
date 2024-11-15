<template>
    <div class=" bg-black text-white p-2 fixed bottom-0 w-full h-17 flex justify-around items-center">
      <NuxtLink to="/" class="flex flex-col items-center">
        <Icon name="heroicons:newspaper" class="w-8 h-8" />
        <span class="text-xs">Лента</span>
      </NuxtLink>
      <NuxtLink to="/documents" class="flex flex-col items-center">
        <Icon name="solar:documents-outline" class="w-8 h-8" />
        <span class="text-xs">Документы</span>
      </NuxtLink>
      <NuxtLink to="/services" class="flex flex-col items-center">
        <Icon name="carbon:web-services-task-definition-version" class="w-8 h-8" />
        <span class="text-xs">Сервисы</span>
      </NuxtLink>
      <NuxtLink to="/menu" class="flex flex-col items-center">
        <Icon name="material-symbols:location-home-outline-rounded" class="w-8 h-8" />
        <span class="text-xs">Меню</span>
      </NuxtLink>
    </div>
  </template>
  
  <script setup>
  </script>
8