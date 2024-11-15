<template>
  <div>
    <RegisterForm />
  </div>
</template>

<script setup>
import { useHead } from '#imports'
import RegisterForm from '~/components/auth/RegisterForm.vue';

useHead({
  title: 'Регистрация', 
  meta: [
    { name: 'description', content: '' },
    { name: 'keywords', content: '' },
  ],
})

definePageMeta({
  layouts: 'auth'
})

</script>

<style scoped>

</style>