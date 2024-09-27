<template>
  <div>
    <div>
      <div class="ButtonContainer">
        <button type="button" class="btn btn-outline-primary" @click="emitNumber('1')">
          1
        </button>
        <button type="button" class="btn btn-outline-secondary" @click="emitNumber('2')">
          2
        </button>
        <button type="button" class="btn btn-outline-success" @click="emitNumber('3')">
          3
        </button>
        <button type="button" class="btn btn-outline-danger" @click="emitNumber('4')">
          4
        </button>
        <button type="button" class="btn btn-outline-warning" @click="emitNumber('5')">
          5
        </button>
        <button type="button" class="btn btn-outline-info" @click="emitNumber('6')">
          6
        </button>
        <button type="button" class="btn btn-outline-success" @click="emitNumber('7')">
          7
        </button>
        <button type="button" class="btn btn-outline-dark" @click="emitNumber('8')">
          8
        </button>
        <button type="button" class="btn btn-outline-success" @click="emitNumber('9')">
          9
        </button>
        <button type="button" class="btn btn-outline-danger" @click="emitNumber('0')">
          0
        </button>
        <button type="button" class="btn btn-outline-warning" @click="emitNumber('.')">
          .
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ButtonsCacl",

  methods: {
    emitNumber(value) {
      this.$emit('button-click', value);
    }
  }
}
</script>

<style scoped>
.ButtonContainer {
  display: grid;
  grid-template-columns: repeat(3, 100px);
  grid-template-rows: repeat(4, 90px);
  font-weight: bold;
  gap: 3px;
}

@media only screen and (max-width: 667px) {
  .ButtonContainer {
    width: 80px;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(4, 1fr);
    width: 60%;
  }

  button {
    font-size: 10px;
    font-weight: bold;
  }
}

button {
  box-shadow: 3px 4px 0px 0px rgba(0, 0, 0, 0.1);
  font-size: 40px;
}

button:nth-child(10) {
  grid-column: 1 / span 2;
}
</style>
