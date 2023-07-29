<script setup>
    const props = defineProps(['operacaoAritmetica', 'trocarOperacao', 'numeroUm', 'numeroDois'])
</script>
<template>
    <form>
        <div class="row">
            <div class="col-3">
                <input @change="props.numeroUm" type="number" placeholder="Digite um número"
                    class="form-control">
            </div>
            <div class="col-1">
                <select @change="props.trocarOperacao" class="form-control">
                    <option value="adicao">+</option>
                    <option value="subtracao">-</option>
                    <option value="multiplicacao">x</option>
                    <option value="divisao">/</option>
                </select>
            </div>
            <div class="col-3">
                <input @change="props.numeroDois" type="number" placeholder="Digite um número"
                    class="form-control">
            </div>
            <div class="col p-1">
                <h3>=</h3>
            </div>
            <div class="col-4 pt-1">
                <h3>{{ props.operacaoAritmetica }}</h3>
            </div>
        </div>
    </form>
</template>