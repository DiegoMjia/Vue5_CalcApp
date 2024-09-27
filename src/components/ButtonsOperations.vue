<template>
  <div>
    <div class="ContainerOperations">
      <button type="button" class="btn btn-primary" @click="EmitValue('CE')">
        CE
      </button>
      <button type="button" class="btn btn-secondary" @click="EmitValue('C')">
        C
      </button>
      <button type="button" class="btn btn-success" @click="EmitValue('/')">
        /
      </button>
      <button type="button" class="btn btn-danger" @click="EmitValue('*')">
        *
      </button>
      <button type="button" class="btn btn-primary" @click="EmitValue('-')">
        -
      </button>
      <button type="button" class="btn btn-secondary" @click="EmitValue('+')">
        +
      </button>
      <button type="button" class="btn btn-danger" @click="EmitValue('=')">
        =
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "ButtonsOperations",

  methods: {
    EmitValue(value) {
      this.$emit("sign-operation", value);
    },
  },
};
</script>

<style scoped>
button {
  font-size: 30px;
}

.ContainerOperations {
  display: grid;
  grid-template-columns: repeat(2, 120px);
  grid-template-rows: repeat(4, 90px);
  gap: 5px;
}

@media only screen and (max-width: 667px) {
  .ContainerOperations {
    grid-template-columns: repeat(2, 1fr);
    grid-template-rows: repeat(4, 1fr);
    gap: 5px;
    height: 100%;
    width: 100%;
    float: left;
  }

  button {
    font-weight: bold;
    font-size: 15px;
    width: 100%;
  }

  button:nth-child(7) {
    grid-column: 1 / span 2;
  }
}

button:nth-child(7) {
  grid-column: 1 / span 2;
}
</style>