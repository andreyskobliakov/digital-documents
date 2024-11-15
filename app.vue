<template>
  <NuxtLayout>
    <NuxtPage />
  </NuxtLayout>
</template>

<script setup>
import { useHead } from '#imports'

useHead({
  titleTemplate: 'Цифровые документы | %s',
})
</script>
