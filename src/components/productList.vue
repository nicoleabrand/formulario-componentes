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
        <p>
          <i class="mdi mdi-delete" @click="$emit('remove', form)" />
        </p>
</template>

<style scoped>
  table {
    width: 50%;
    border-collapse: collapse;
  }

  th,
  td {
    border: 1px solid gray;
    padding: 10px;
  }

  th {
    background-color: lightgray;
  }

  tr {
    text-align: center;
  }

  tr i {
    cursor: pointer;
    font-size: larger;
  }
</style>