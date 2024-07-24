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
const blabla= ref(false)

function adicionar(dados) {
  Object.assign(form, dados)
  console.log(form)
  if (form.nome === '' || form.email === '' || form.senha == '') {
    alert('Os campos nome, e-mail e senha são obrigatórios')
  }
  else if(form.senha!=form.confisenha){
    alert('Os campos senha e confirmação de senha não correspondem')
  }
    else{blabla.value = !blabla.value
    }
  }



</script>

<template>
  <div>
  <h1>Formulário</h1></div>
  <div class="flex-container">
  <product-add @adicionar="adicionar"/> </div>
  <div v-if="blabla" class="flex-container">
  <product-list :form="form" @adicionar="adicionar"/>
</div>

</template>

<style scoped>
h1{
  text-align: center;
  font-family:'Times New Roman', Times, serif ;
}
div, .flex-container{
  border-radius: 10px;
  width: 70%;
  margin: auto;
  display: flex;
  flex-direction: column;
  background-color: gray;
}

</style>
