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

import LoginForm from '~/components/auth/LoginForm.vue';
import BaseTooltip from '~/components/BaseTooltip.vue';

</script>

<style scoped>

</style>
