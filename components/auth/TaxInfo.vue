<template>
  <div class="sm:col-span-2">
    <BaseInput
      v-model="form.inn"
      label="РНОКПП (ИНН)"
      id="inn"
      :placeholder="'Введите ваш идентификационный налоговый номер'"
      :error="errors.inn"
      :helperText="'Введите ваш РНОКПП (ИНН)'"
      :tooltipMessage="'Ваш идентификационный налоговый номер.'"
    />
  </div>
</template>

<script setup>
import BaseInput from '~/components/BaseInput.vue';

const props = defineProps({
  form: Object,
  errors: Object
});
</script>

<style scoped>

</style>
