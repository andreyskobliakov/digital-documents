<template>
  <div class="grid grid-cols-1 gap-4 sm:grid-cols-2 sm:col-span-2">
    <BaseInput
      v-model="form.passportNumber"
      label="Серия и номер"
      id="passportNumber"
      :placeholder="'Введите серию и номер паспорта'"
      :error="errors.passportNumber"
      :helperText="'Введите серию и номер паспорта'"
      :tooltipMessage="'Серия и номер вашего паспорта.'"
    />
    <BaseInput
      v-model="form.passportIssuedBy"
      label="Кем и когда выдан"
      id="passportIssuedBy"
      :placeholder="'Введите орган, выдавший паспорт, и дату выдачи'"
      :error="errors.passportIssuedBy"
      :helperText="'Введите орган, выдавший паспорт, и дату выдачи'"
      :tooltipMessage="'Орган, выдавший паспорт, и дата выдачи.'"
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
