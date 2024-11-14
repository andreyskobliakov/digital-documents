<template>
  <div class="grid grid-cols-1 gap-4 sm:grid-cols-2 sm:col-span-2">
    <BaseInput
      v-model="form.lastName"
      label="Фамилия"
      id="lastName"
      :placeholder="'Введите вашу фамилию'"
      :error="errors.lastName"
      :helperText="'Введите вашу фамилию'"
      :tooltipMessage="'Ваша официальная фамилия, как указано в документах.'"
    />
    <BaseInput
      v-model="form.firstName"
      label="Имя"
      id="firstName"
      :placeholder="'Введите ваше имя'"
      :error="errors.firstName"
      :helperText="'Введите ваше имя'"
      :tooltipMessage="'Ваше первое имя, как указано в документах.'"
    />
    <BaseInput
      v-model="form.middleName"
      label="Отчество"
      id="middleName"
      :placeholder="'Введите ваше отчество'"
      :error="errors.middleName"
      :helperText="'Введите ваше отчество'"
      :tooltipMessage="'Ваше отчество, как указано в документах.'"
      class="sm:col-span-2"
    />
    <BaseInput
      v-model="form.birthDate"
      label="Дата рождения"
      id="birthDate"
      type="date"
      :placeholder="'ДД.ММ.ГГГГ'"
      :error="errors.birthDate"
      :helperText="'Выберите вашу дату рождения'"
      :tooltipMessage="'Введите вашу дату рождения в формате ДД.ММ.ГГГГ.'"
      class="sm:col-span-2"
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
