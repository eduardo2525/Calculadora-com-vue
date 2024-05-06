<script setup>
    const props = defineProps(['operacao', 'firtsNumber', 'secondNumber'])
</script>

<template>
    <div class="row">
        <div class="col-xl-4 col-sm-12">
            <input @keyup="props.firtsNumber" type="number" placeholder="Digite o primeiro número" required>
        </div>
        <div class="col-xl-4 col-sm-12">
            <input @keyup="props.secondNumber" type="number" placeholder="Digite o primeiro número" required>
        </div>
    </div>
    <div class="col-xl-4 col-sm-12">
        <select @change="props.operacao">
            <option value="adicao">Adição</option>
            <option value="subtracao">Subtração</option>
            <option value="multiplicacao">Multiplicação</option>
            <option value="divisao">Divisão</option>
        </select>
    </div>
</template>

<style scoped>
    .row {
        margin: 0 auto;
    }
    .col-xl-4 {
        margin-top: 30px;
    }
    .col-sm-12 {
        display: flex;
        justify-content: center;
    }
</style>