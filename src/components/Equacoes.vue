<script setup>
    const props = defineProps(['tipoEquacao'])
</script>
<template>
    <div class="row">
        <div class="col">
            <select @change="props.tipoEquacao" class="form-control mb-4">
                <option value="soma">Soma</option>
                <option value="subtracao">Subtração</option>
                <option value="divisao">Divisão</option>
                <option value="multiplicacao">Multiplicação</option>
            </select>
        </div>
    </div>
</template>