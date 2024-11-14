<template>
  <div class="min-h-screen flex items-center justify-center p-4">
    <div class="bg-white bg-opacity-50 p-8 rounded-lg shadow-lg w-full max-w-2xl">
      <h1 class="text-2xl font-bold mb-6 flex justify-center">Регистрация</h1>
      <form @submit.prevent="submitForm" class="grid grid-cols-1 gap-6 sm:grid-cols-2">
        <PersonalInfo :form="form" :errors="errors" />
        <AddressInfo :form="form" :errors="errors" />
        <PassportInfo :form="form" :errors="errors" />
        <TaxInfo :form="form" :errors="errors" />

        <!-- Поля для PIN-кода -->
        <div class="sm:col-span-2">
          <BaseInput
            v-model="form.pinCode"
            label="PIN код"
            id="pinCode"
            type="password"
            :placeholder="'Введите ваш PIN код'"
            :error="errors.pinCode"
            :helperText="'PIN код должен быть 4 цифры'"
            :tooltipMessage="'Ваш 4-значный PIN код, используемый для входа.'"
          />
          <BaseInput
            v-model="form.confirmPinCode"
            label="Подтвердите PIN код"
            id="confirmPinCode"
            type="password"
            :placeholder="'Повторите ваш PIN код'"
            :error="errors.confirmPinCode"
            :helperText="'Повторите ваш PIN код для подтверждения'"
            :tooltipMessage="'Повторите ваш 4-значный PIN код, чтобы убедиться, что он введен правильно.'"
          />
        </div>

        <!-- Кнопка отправки -->
        <div class="sm:col-span-2">
          <button type="submit" class="w-full bg-blue-500 text-white py-2 rounded-lg shadow-lg hover:bg-blue-600 transition duration-300 ease-in-out">Зарегистрироваться</button>
        </div>
      </form>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import PersonalInfo from '~/components/auth/PersonalInfo.vue';
import AddressInfo from '~/components/auth/AddressInfo.vue';
import PassportInfo from '~/components/auth/PassportInfo.vue';
import TaxInfo from '~/components/auth/TaxInfo.vue';
import BaseInput from '~/components/BaseInput.vue';

const form = ref({
  lastName: '',
  firstName: '',
  middleName: '',
  birthDate: '',
  country: '',
  city: '',
  street: '',
  house: '',
  apartment: '',
  passportNumber: '',
  passportIssuedBy: '',
  inn: '',
  pinCode: '',
  confirmPinCode: ''
});

const errors = ref({
  lastName: '',
  firstName: '',
  middleName: '',
  birthDate: '',
  country: '',
  city: '',
  street: '',
  house: '',
  apartment: '',
  passportNumber: '',
  passportIssuedBy: '',
  inn: '',
  pinCode: '',
  confirmPinCode: ''
});

const submitForm = () => {
  validateForm();
  if (Object.keys(errors.value).length === 0) {
    console.log('Форма отправлена', form.value);
  } else {
    console.log('Форма содержит ошибки');
  }
};

const validateForm = () => {
  errors.value = {};
  if (!form.value.pinCode.match(/^\d{4}$/)) {
    errors.value.pinCode = 'PIN код должен быть 4 цифры';
  }
  if (form.value.pinCode !== form.value.confirmPinCode) {
    errors.value.confirmPinCode = 'PIN коды не совпадают';
  }
};
</script>

<style scoped>

</style>