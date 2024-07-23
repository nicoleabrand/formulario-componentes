<script setup>
  defineProps(['form']);
</script>

<template>
        <p>Nome: {{ form.nome }}</p>
        <p>Email: {{ form.email }}</p>
        <p>Data de nascimento: {{ form.datanasc }}</p>
        <p>Endereço: {{ form.endereco }}</p>
        <p>Cidade: {{ form.cidade }}</p>
        <p>Estado: {{ form.estado }}</p>
        <p>Hobbies: {{ form.hobbies }}</p>
        <p>Linguagens de programação:{{ form.lingprog }}</p>
        <p>Biografia:{{ form.bio }}</p>
</template>

<style scoped>

</style>