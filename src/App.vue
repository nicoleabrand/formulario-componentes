<script setup>
import { ref, reactive } from 'vue'
import ProductList from '@/components/productList.vue'
import ProductAdd from '@/components/productAdd.vue'

function removerItem(id) {
  const index = produtos.value.findIndex((produto) => produto.id === id)
  produtos.value.splice(index, 1)
}
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
function adicionar(dados) {
  Object.assign(form, dados)
  console.log(form)
}
</script>

<template>
  <h1>Meus produtos</h1>
  <product-add @adicionar="adicionar" />
  <product-list :form="form" @excluir="excluir" @apagarTudo="excluirTodos" @adicionar="adicionar" />
</template>

<style scoped></style>
