<template>
  <div class="output">
    <div class="output__prev">{{ `${prev} ${operation}`}}</div>
    <div class="output__current">{{ current }}</div>
  </div>
</template>

<script>
export default {
  props: {
    prev: {
      type: String,
      required: true
    },
    current: {
      type: String,
      required: true
    },
    operation: {
      type: String,
      required: true
    }
  }
}
</script>

<style>
.output {
  width: 288px;
  min-height: 149px;
  background: #ffffff;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  border-radius: 20px;
  padding: 25px 0;
  color: #000000;
  user-select: none;

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
  word-wrap: break-word;
  word-break: break-all;
}

.output__prev {
  min-height: 22px;
  font-size: 18px;
  line-height: 22px;
  font-style: normal;
  font-weight: 700;
}

.output__current {
  min-height: 77px;
  font-size: 64px;
  line-height: 77px;
  font-style: normal;
  font-weight: 700;
}
</style>