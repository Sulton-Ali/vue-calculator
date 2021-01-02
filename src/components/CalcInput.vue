<template>
  <div class="buttons">
    <button :class="button.class" 
      v-for="button in buttons" 
      :key="button.value">
      {{ button.value }}
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      buttons: [
        { value: "C", class: "buttons__item" },
        { value: "+/-", class: "buttons__item" },
        { value: "%", class: "buttons__item" },
        { value: "➗", class: "buttons__item" },
        { value: "7", class: "buttons__item" },
        { value: "8", class: "buttons__item" },
        { value: "9", class: "buttons__item" },
        { value: "x", class: "buttons__item" },
        { value: "4", class: "buttons__item" },
        { value: "5", class: "buttons__item" },
        { value: "6", class: "buttons__item" },
        { value: "-", class: "buttons__item" },
        { value: "1", class: "buttons__item" },
        { value: "2", class: "buttons__item" },
        { value: "3", class: "buttons__item" },
        { value: "+", class: "buttons__item v-double" },
        { value: "0", class: "buttons__item" },
        { value: ".", class: "buttons__item" },
        { value: "=", class: "buttons__item" },
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
  border-radius: 50%;
  background: #f5bd89;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  outline: none;
  border: none;
  font-size: 18px;
  line-height: 22px;
  
  transition: all 0.3s ease-out;;
}

.calculator--dark .buttons__item {
  background: #545353;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  color: #F5BD89;
}

.v-double {
  grid-column: 4;
  grid-row: 4 / span 2;
  border-radius: 50px;
}
</style>