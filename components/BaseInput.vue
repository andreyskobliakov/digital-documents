<template>
  <div class="mb-4 w-full relative">
    <label :for="id" class=" text-gray-700 font-semibold mb-2 flex items-center justify-between">
      {{ label }}
    </label>
    <div class="relative flex items-center">
      <input
        :type="type"
        :id="id"
        :placeholder="placeholder"
        :value="modelValue"
        @input="$emit('update:modelValue', $event.target.value)"
        class="w-full px-3 py-2 border border-gray-300 rounded-lg focus:outline-none focus:border-blue-500 mt-2"
      />
      <BaseTooltip v-if="tooltipMessage" :message="tooltipMessage" class="absolute right-0 mr-2" />
    </div>
    <p v-if="error" class="text-sm text-red-500 mt-1">{{ error }}</p>
  </div>
</template>

<script setup>
import BaseTooltip from '~/components/BaseTooltip.vue';

const props = defineProps({
  modelValue: String,
  label: String,
  type: {
    type: String,
    default: 'text'
  },
  id: String,
  placeholder: String,
  helperText: {
    type: String,
    default: ''
  },
  error: {
    type: String,
    default: ''
  },
  tooltipMessage: {
    type: String,
    default: ''
  }
});
</script>

<style scoped>

</style>
