<template>
  <div class="flex flex-col items-center justify-center min-h-screen relative">
    <div class="relative flex items-center mb-6">
      <h1 class="text-3xl">Код для входа</h1>
      <BaseTooltip message="Ваш код для входа использовался при регистрации" />
    </div>
    <LoginForm />
  </div>
</template>

<script setup>
import { useHead } from '#imports'
import LoginForm from '~/components/auth/LoginForm.vue'
import BaseTooltip from '~/components/BaseTooltip.vue'

useHead({
  title: 'Вход', 
  meta: [
    { name: 'description', content: '' },
    { name: 'keywords', content: '' },
  ],
})

definePageMeta({
  layout: 'auth',
})
</script>

<style scoped>

</style>
