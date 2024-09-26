<template>
  <div>
    <div class="Screen">
      {{ NumberValue }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'ScreenCalc',
  props: ['NumberValue', 'ResponseValue'],
}
</script>

<style scoped>
.Screen {
  border: 2px solid #000;
  width: 560px;
  height: 120px;
  font-size: 50px;
  text-align: end;
}

.OperationValue {
  position: relative;
  float: right;
}

.ScreenResponse {
  height: 30px;
  width: 70%;
  border: 2px solid #000;
  border-top: none;
  position: relative;
  left: 166px;
  font-size: 20px;
}
</style>