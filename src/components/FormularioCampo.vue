<template>
    <div class="col-5 m-auto">
        <label :for='nome' class='form-label'>{{ nome }}</label>
        <input type='text' class="py-1 m-2 form-control" :placeholder='nome' :id='nome' :value='modelValue' @input='$emit("update:modelValue", $event.target.value)' @keypress.enter='adicionar'>
    </div>
</template>

<script>
export default {
    name: 'FormularioCampo',
    props: {
        nome: String,
        adicionar: {type:Function},
        modelValue: String
    },
    emits: ['update:modelValue']
}
</script>

<style>

</style>
