<template>
    <div class="flex flex-col items-center justify-center h-full p-4 m-4">
      <div class="flex m-8 space-x-4">
        <input
          v-for="(digit, index) in pinCode"
          :key="index"
          type="password"
          maxlength="1"
          class="w-4 h-4 border-2 border-gray-300 rounded-full shadow-md text-center text-xl focus:outline-none"
          :class="{ 'bg-black': digit !== '', 'bg-white': digit === '' }"
          v-model="pinCode[index]"
          @input="handleInput(index)"
          @keydown="handleKeyDown(index, $event)"
        />
      </div>
      
      <div class="grid grid-cols-3 gap-8 m-8">
        <button
          v-for="n in [1, 2, 3, 4, 5, 6, 7, 8, 9]"
          :key="n"
          :class="buttonClass(n)"
          @click="handleButtonClick(n)"
        >
          {{ n }}
        </button>
        <button
          :class="buttonClass(0)"
          @click="handleButtonClick(0)"
        >
          0
        </button>
        <button
          class="w-16 h-16 text-3xl bg-yellow-500 text-white rounded-full shadow-lg hover:bg-yellow-600 transition duration-300 ease-in-out transform hover:scale-105 col-start-3"
          @click="handleBackspace"
        >
          ←
        </button>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref, nextTick } from 'vue';
  
  const pinCode = ref(['', '', '', '']);
  const activeButton = ref(null);
  
  const handleButtonClick = (number) => {
    const emptyIndex = pinCode.value.findIndex(digit => digit === '');
    if (emptyIndex !== -1) {
      pinCode.value[emptyIndex] = number.toString();
      if (emptyIndex < pinCode.value.length - 1) focusNextInput(emptyIndex);
    }
  
    if (pinCode.value.every(digit => digit !== '')) {
      console.log('Введенный пин-код:', pinCode.value.join(''));
    }
    highlightButton(number);
  };
  
  const highlightButton = (number) => {
    activeButton.value = number;
    setTimeout(() => activeButton.value = null, 200);
  };
  
  const handleBackspace = () => {
    const filledIndex = pinCode.value.slice().reverse().findIndex(digit => digit !== '');
    if (filledIndex !== -1) {
      pinCode.value[pinCode.value.length - 1 - filledIndex] = '';
      focusNextInput(pinCode.value.length - 2 - filledIndex);
    }
  };
  
  const focusNextInput = async (index) => {
    await nextTick();
    const nextInput = document.querySelectorAll("input")[index + 1];
    if (nextInput) nextInput.focus();
  };
  
  const handleKeyDown = (index, event) => {
    const { key } = event;
    if (key >= '0' && key <= '9') {
      handleButtonClick(parseInt(key));
    } else if (key === 'Backspace') {
      handleBackspace();
    }
  };
  
  const buttonClass = (n) => [
    'w-16 h-16 text-3xl border-2 rounded-full shadow-lg transition duration-300 ease-in-out transform hover:scale-105',
    activeButton.value === n ? 'bg-black text-white' : 'bg-white text-black border-gray-300'
  ];
  </script>
  <style scoped>

</style>
  