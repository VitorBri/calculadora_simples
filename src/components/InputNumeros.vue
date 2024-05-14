<script setup>
    const props = defineProps(['primeiroNumero','segundoNumero'])
</script>
<template>
    <div class="row">
        <div class="col">
            <input @keyup="props.primeiroNumero" required type="number"
                placeholder="Coloque o primeiro número" class="form-control mb-4">
        </div>
    </div>
    <div class="row">
        <div class="col">
            <input @keyup="props.segundoNumero" required type="number"
                placeholder="Coloque o segundo número" class="form-control mb-4">
        </div>
    </div>
</template>