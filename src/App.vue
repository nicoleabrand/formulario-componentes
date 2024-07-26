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
const save= ref(false)

function adicionar(dados) {
  Object.assign(form, dados)
  console.log(form)
  if (form.nome === '' || form.email === '' || form.senha == '') {
    alert('Os campos nome, e-mail e senha são obrigatórios')
  }
  else if(form.senha!=form.confisenha){
    alert('Os campos senha e confirmação de senha não correspondem')
  }
    else{save.value = !save.value
    }
  }



</script>

<template>
    <!-- arrumar colunas do flex container -->
  <div class="flex-container">
    <h1>Formulário</h1>
    <product-add @adicionar="adicionar"/>
  </div>
    <div v-if="save" class="flex-container">
      <product-list :form="form" @adicionar="adicionar"/>
  </div>
</template>

<style scoped>
h1{
  margin: auto;
  font-family: "Roboto Slab", serif;
}
div, .flex-container{
  width: 50%;
  display: flex;
  justify-content: end;
  flex-direction: column;
  column-gap: 10%;
  background-color: rgb(185, 124, 124);
  border-radius: 3%;
}

</style>
