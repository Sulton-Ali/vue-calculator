<template>
  <div :class="`calculator ${ isDark ? 'calculator--dark' : '' }`">
    <CalcOutput class="calculator__output" />
    <CalcInput class="calculator__input" />
    <button class="toggle-theme" @click="toggleHandle"></button>
  </div>
</template>

<script>
import CalcOutput from './CalcOutput'
import CalcInput from './CalcInput'
export default {
  components: {
    CalcOutput,
    CalcInput
  },
  data() {
    return {
      isDark: true
    }
  },
  methods: {
    toggleHandle() {
      this.isDark = !this.isDark
    }
  }
}
</script>

<style>
.calculator {
  width: 320px;
  margin: 0 auto;
  padding: 25px 0 10px;
  background-color: #F5BD89;

  border-radius: 5px;
  transition: all 0.3s ease-out;
}

.calculator--dark {
  background-color: rgba(0, 0, 0, 0.82);;
}

.calculator__output {
  margin: 0 auto;
}

.calculator__input {
  margin: 0 auto;
  margin-top: 21px;
  margin-bottom: 21px;
}

.toggle-theme {
  width: 34px;
  height: 21px;
  background-color: transparent;
  background-image: url('../assets/toggle-light.svg');
  background-size: cover;

  border: none;
  outline: none;
  cursor: pointer;

  transition: all 0.3s ease-out;
}

.calculator--dark .toggle-theme {
  background-color: transparent;
  background-image: url('../assets/toggle-dark.svg');
}


</style>