<script setup>
defineProps(['form'])
</script>
<template>
  <div class="resultado">
    <h1>Informações</h1>
    <p>Nome: {{ form.nome }}</p>
    <p>Email: {{ form.email }}</p>
    <p>Data de nascimento: {{ form.datanasc }}</p>
    <p>Endereço: {{ form.endereco }}</p>
    <p>Cidade: {{ form.cidade }}</p>
    <p>Estado: {{ form.estado }}</p>
    <p>Hobbies: {{ form.hobbies }}</p>
    <p>Linguagens de programação: {{ form.lingprog }}</p>
    <p>Biografia: {{ form.bio }}</p>
  </div>
</template>

<style scoped>
h1 {
  font-family: 'Roboto Slab', serif;
  font-size: 150%;
  margin: 1%;
}
p {
  font-family: 'Montserrat', sans-serif;
}

.resultado {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-items: flex-start;
  gap: 0.2rem;

  & p {
    margin: 0.4rem;
  }
}
</style>
