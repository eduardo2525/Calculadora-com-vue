<script setup>
    const props = defineProps(['firtsNumber', 'secondNumber', 'resultado'])
</script>

<template>
    <div class="row container__calculo">
        <div class="calculo">
            <span v-if="props.firtsNumber && props.secondNumber != ''">
                Resultado: {{ props.resultado }}
            </span>
            <span v-else-if="props.firtsNumber === '' || props.secondNumber === ''">
                Digite os Dois números
            </span>
        </div>
    </div>
</template>

<style scoped>
    .container__calculo {
        display: flex;
        justify-content: center;
    }
    .calculo {
        margin: 30px;
        width: 400px;
        height: 50px;
        border-radius: 15px;
        background-color: rgb(0, 225, 255);
        display: flex;
        justify-content: center;
        align-items: center;
    }
    span {
        color: rgb(12, 11, 11);
        font-size: 30px;
    }
</style>