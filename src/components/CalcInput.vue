<template>
  <div class="buttons">
    <div :class="button.class"
      :data-type="button.type"
      v-for="button in buttons" 
      :key="button.value"
      @click="buttonClick"
    >
      {{ button.value }}
    </div>
  </div>
</template>

<script>
export default {
  props: {
    buttonClick: {
      type: Function
    }
  },
  data() {
    return {
      buttons: [
        { value: "C", class: "buttons__item", type: 'clear' },
        { value: "+/-", class: "buttons__item", type: 'operation' },
        { value: "%", class: "buttons__item", type: 'operation' },
        { value: "÷", class: "buttons__item", type: 'operation' },
        { value: "7", class: "buttons__item", type: 'number' },
        { value: "8", class: "buttons__item", type: 'number' },
        { value: "9", class: "buttons__item", type: 'number' },
        { value: "x", class: "buttons__item", type: 'operation' },
        { value: "4", class: "buttons__item", type: 'number' },
        { value: "5", class: "buttons__item", type: 'number' },
        { value: "6", class: "buttons__item", type: 'number' },
        { value: "-", class: "buttons__item", type: 'operation' },
        { value: "1", class: "buttons__item", type: 'number' },
        { value: "2", class: "buttons__item", type: 'number' },
        { value: "3", class: "buttons__item", type: 'number' },
        { value: "+", class: "buttons__item v-double", type: 'operation' },
        { value: "0", class: "buttons__item", type: 'number' },
        { value: ".", class: "buttons__item", type: 'number' },
        { value: "=", class: "buttons__item", type: 'equal' },
      ]
    }
  },
};
</script>

<style>
.buttons {
  width: 266px;
  display: grid;
  grid-template-rows: repeat(5, 50px);
  grid-template-columns: repeat(4, 50px);
  column-gap: 22px;
  row-gap: 10px;
}
.buttons__item {
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 50%;
  background: #f5bd89;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  outline: none;
  border: none;
  font-size: 18px;
  line-height: 22px;
  cursor: pointer;
  user-select: none;
  
  transition: all 0.3s ease-out;;
}

.buttons__item:hover {
  background-color: gold;
}

.buttons__item:active {
  transition: all 0.1s linear;
  transform: translate(0, 2px);
  box-shadow: none;
}

.calculator--dark .buttons__item {
  background: #545353;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  color: #F5BD89;
}

.calculator--dark .buttons__item:hover {
  background-color: cornflowerblue;
}

.v-double {
  grid-column: 4;
  grid-row: 4 / span 2;
  border-radius: 50px;
}
</style>