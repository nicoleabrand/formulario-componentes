<script setup>
import { ref, reactive } from 'vue'
import ProductList from '@/components/productList.vue'
import ProductAdd from '@/components/productAdd.vue'

const form = reactive({
  nome: '',
  email: '',
  senha: '',
  confisenha: '',
  datanasc: '',
  endereco: '',
  cidade: '',
  estado: [],
  hobbies: '',
  lingprog: '',
  bio: ''
})
const save = ref(false)

function adicionar(dados) {
  Object.assign(form, dados)
  console.log(form)
  if (form.nome === '' || form.email === '' || form.senha == '') {
    alert('Os campos nome, e-mail e senha são obrigatórios')
  } else if (form.senha != form.confisenha) {
    alert('Os campos senha e confirmação de senha não correspondem')
  } else {
    save.value = !save.value
  }
}
</script>

<template>
  <!-- arrumar colunas do flex container -->
  <h1>Formulário</h1>
  <div class="flex-container">
    <product-add class="flex-item" @adicionar="adicionar" />
    <product-list class="flex-item" v-if="save" :form="form" @adicionar="adicionar" />
  </div>
</template>

<style scoped>
h1 {
  margin: auto;
  font-family: 'Roboto Slab', serif;
  text-align: center;
  font-size: 300%;
  padding: 1%;
}

.flex-container {
  width: 100%;
  display: flex;
  justify-content: space-between;
  flex-direction: row;

  row-gap: 2rem;
}

.flex-item {
  width: 49%;
  background-color: rgb(185, 124, 124);
  border-radius: 3%;
}
</style>
