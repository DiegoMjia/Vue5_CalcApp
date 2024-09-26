<template>
    <div>
        <div class="ContainerOperations">
            <button type="button" class="btn btn-primary" @click="EmitValue('CE')">CE</button>
            <button type="button" class="btn btn-secondary" @click="EmitValue('C')">C</button>
            <button type="button" class="btn btn-success" @click="EmitValue('/')">/</button>
            <button type="button" class="btn btn-danger" @click="EmitValue('*')">*</button>
            <button type="button" class="btn btn-primary" @click="EmitValue('-')">-</button>
            <button type="button" class="btn btn-secondary" @click="EmitValue('+')">+</button>
            <button type="button" class="btn btn-danger" @click="EmitValue('=')"> = </button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ButtonsOperations',

    methods: {
        EmitValue (value) {
            this.$emit('sign-operation', value);
        }
    }
}
</script>

<style scoped>
button {
    font-size: 30px;
    grid-area: 5px;
}

.ContainerOperations {
    display: grid;
    grid-template-columns: repeat(2, 120px);
    grid-template-rows: repeat(4, 90px);
    gap: 5px;
}

button:nth-child(7) {
    grid-column: 1 / span 2;
}
</style>