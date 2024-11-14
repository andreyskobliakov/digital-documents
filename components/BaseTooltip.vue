<template>
  <div class="relative flex items-center">
    <div class="group relative flex items-center">
      <Icon name="lsicon:circle-information-outline" class="w-5 h-5 cursor-pointer text-black ml-2" />
      <div class="absolute right-full mr-2 mt-2 hidden group-hover:block w-64 p-2 bg-gray-800 text-white text-sm rounded-lg shadow-lg">
        {{ message }}
        <div class="absolute left-full top-1/2 transform -translate-y-1/2 w-0 h-0 border-t-8 border-t-transparent border-b-8 border-b-transparent border-r-8 border-r-gray-800"></div>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  message: {
    type: String,
    required: true
  }
});
</script>

<style scoped>

</style>