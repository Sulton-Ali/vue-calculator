<template>
  <div :class="`calculator ${ isDark ? 'calculator--dark' : '' }`">
    <CalcOutput class="calculator__output" 
      v-bind:prev="prev"
      v-bind:current="current"
      v-bind:operation="operation"
    />
    <CalcInput class="calculator__input" 
      v-bind:buttonClick="buttonClick"
    />
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
      prev: '',
      current: '',
      operation: '',
      isDark: false
    }
  },
  methods: {
    toggleHandle() {
      this.isDark = !this.isDark
    },
    addNumber(number) {
      if (number.toString() === '.' && this.current.includes('.')) return;
      if (this.current.length >= 8) return;
      this.current = this.current + number;
    },
    compute() {
      switch(this.operation) {
        case '+': {
          this.current = parseFloat(this.prev) + parseFloat(this.current);
          break;
        }
        case '-': {
          this.current = parseFloat(this.prev) - parseFloat(this.current);
          break;
        }
        case '÷': {
          this.current = parseFloat(this.prev) / parseFloat(this.current);
          break;
        }
        case 'x': {
          this.current = parseFloat(this.prev) * parseFloat(this.current);
          break;
        }
        case '%': {
          this.current = parseFloat(this.prev) % parseFloat(this.current);
          break;
        }
        default: {}
      }
      this.prev = '';
      this.operation = '';
    },
    makeOperation(operation) {
      if (this.prev && this.current) {
        this.compute();
      }
      this.operation = operation;
      if (this.current === '') return;
      this.prev = this.current;
      this.current = '';
    },
    clear() {
      this.prev = '';
      this.current = '';
      this.operation = '';
    },
    buttonClick(e) {
      const type = e.target.getAttribute('data-type');
      const value = e.target.innerText;
      
      switch(type) {
        case 'number': {
          this.addNumber(value)
          break;
        }
        case 'operation': {
          this.makeOperation(value)
          break;
        }
        case 'clear': {
          this.clear()
          break;
        }
        case 'equal': {
          this.compute();
          break;
        }
        default: {
          console.log('default')
        }
      }
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