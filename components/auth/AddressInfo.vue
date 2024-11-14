<template>
  <div class="grid grid-cols-1 gap-4 sm:grid-cols-2 sm:col-span-2">
    <BaseInput
      v-model="form.country"
      label="Страна"
      id="country"
      :placeholder="'Введите вашу страну проживания'"
      :error="errors.country"
      :helperText="'Введите вашу страну проживания'"
      :tooltipMessage="'Страна, в которой вы проживаете.'"
    />
    <BaseInput
      v-model="form.city"
      label="Город"
      id="city"
      :placeholder="'Введите ваш город проживания'"
      :error="errors.city"
      :helperText="'Введите ваш город проживания'"
      :tooltipMessage="'Город, в котором вы проживаете.'"
    />
    <BaseInput
      v-model="form.street"
      label="Улица"
      id="street"
      :placeholder="'Введите вашу улицу проживания'"
      :error="errors.street"
      :helperText="'Введите вашу улицу проживания'"
      :tooltipMessage="'Улица, на которой вы проживаете.'"
    />
    <BaseInput
      v-model="form.house"
      label="Дом"
      id="house"
      :placeholder="'Введите номер вашего дома'"
      :error="errors.house"
      :helperText="'Введите номер вашего дома'"
      :tooltipMessage="'Номер вашего дома.'"
    />
    <BaseInput
      v-model="form.apartment"
      label="Квартира"
      id="apartment"
      :placeholder="'Введите номер вашей квартиры'"
      :error="errors.apartment"
      :helperText="'Введите номер вашей квартиры'"
      :tooltipMessage="'Номер вашей квартиры.'"
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
