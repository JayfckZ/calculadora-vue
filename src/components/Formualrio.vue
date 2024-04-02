<script setup>
    const props = defineProps(['primeiroValor', 'segundoValor', 'mudaAcao', 'operacao'])
</script>

<template>
    <section>
        <div class="row">
            <div class="col-sm-3 col-md-5"></div>

            <form class="col-sm-6 col-md-2 bg-light p-4 rounded mt-2">
                <input type="number" class="form-control text-center" placeholder="Primeiro número" value="0" @keyup="props.primeiroValor">
                <select class="form-control mt-2 text-center" @change="props.mudaAcao">
                    <option value="adicao">Somar</option>
                    <option value="subtracao">Subtrair</option>
                    <option value="multiplicacao">Multiplicar</option>
                    <option value="divisao">Dividir</option>
                </select>
                <input type="number" class="form-control text-center mt-2 mb-3" placeholder="Segundo número" value="0" @keyup="props.segundoValor">

                <h5>Resultado:</h5>
                <h4 class="text-center mt-4">{{ props.operacao }}</h4>
            </form>

            <div class="col-sm-3 col-md-5"></div>
        </div>
    </section>
</template>