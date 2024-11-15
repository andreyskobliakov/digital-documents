<template>
  <div class="min-h-screen flex flex-col">
    <div class="container mx-auto p-6">
      <div>
        <Breadcrumbs />
      </div>
      <slot />
    </div>
    <BottomMenu />
  </div>
</template>

<script setup>
import BottomMenu from '~/components/BottomMenu.vue';
</script>
