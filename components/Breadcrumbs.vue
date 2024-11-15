<template>
  <nav
    aria-label="Хлебные крошки"
    class="flex items-center space-x-3 text-gray-700 text-sm font-medium"
    v-if="route.path !== '/'"
  >
    <router-link
      to="/"
      class="hover:text-indigo-500 transition duration-200 ease-in-out transform hover:scale-105"
    >
      Главная
    </router-link>

    <span v-if="breadcrumbs.length > 0" class="text-gray-400">/</span>

    
    <router-link
      v-for="(crumb, index) in breadcrumbs"
      :key="crumb.path"
      :to="crumb.path"
      class="hover:text-indigo-500 transition duration-200 ease-in-out transform hover:scale-105"
    >
      <span v-if="index > 0" class="text-gray-400">/</span>
      <span>{{ crumb.name }}</span>
    </router-link>
  </nav>
</template>

<script setup>
import { useRoute } from 'vue-router'
import { computed } from 'vue'

const route = useRoute()


const breadcrumbs = computed(() => {
  
  return route.matched
    .map((segment) => {
      const breadcrumb = segment.meta.breadcrumb
      return breadcrumb ? { name: breadcrumb.name, path: segment.path } : null
    })
    .filter(Boolean) 
})
</script>

<style scoped>

nav {
  @apply text-gray-700 text-sm font-medium flex items-center space-x-3;
}

router-link {
  @apply hover:text-indigo-500 transition duration-200 ease-in-out transform hover:scale-105;
}

span {
  @apply text-gray-400;
}

router-link:hover {
  @apply text-indigo-500;
  transform: scale(1.05);
}
</style>
