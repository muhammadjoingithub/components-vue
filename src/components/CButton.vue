<template>
  <button @click="toggleColor" :style="{ backgroundColor: buttonColor }" class="mt-20 mx-auto w-200 center">
    {{ buttonText }}
  </button>
</template>

<script>
export default {
  data() {
    return {
      buttonColor: 'red',
      buttonText: 'Click me'
    };
  },
  methods: {
    toggleColor() {
      if (this.buttonColor === 'red') {
        this.buttonColor = 'yellow';
      } else {
        this.buttonColor = 'red';
      }
    }
  }
};
</script>

<style scoped>
button {
  padding: 10px 20px;
  font-size: 16px;
  color:red;
  outline: none;
  border: none;
  cursor: pointer;
  border-radius: 10px;
}
</style>