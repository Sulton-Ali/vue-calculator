<template>
  <div class="output">
    <div class="output__prev">622/10</div>
    <div class="output__current">62.2</div>
  </div>
</template>



<style>
.output {
  width: 288px; 
  background: #ffffff;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  border-radius: 20px;
  padding: 25px 0;
  color: #000000;

  transition: all 0.3s ease-out;
}

.calculator--dark .output {
  background: rgba(175, 175, 175, 0.26);
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  color: #F5BD89;
}

.output__prev,
.output__current {
  width: 100%;
  text-align: center;
}

.output__prev {
  font-size: 18px;
  line-height: 22px;
  font-style: normal;
  font-weight: 700;
}

.output__current {
  font-size: 64px;
  line-height: 77px;
  font-style: normal;
  font-weight: 700;
}
</style>