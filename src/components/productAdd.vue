<script setup>
import { reactive } from 'vue'
const emit = defineEmits(['adicionar'])
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
const estados = [
  {
    sigla: 'AC',
    nome: 'Acre'
  },
  {
    sigla: 'AL',
    nome: 'Alagoas'
  },
  {
    sigla: 'AP',
    nome: 'Amapá'
  },
  {
    sigla: 'AM',
    nome: 'Amazonas'
  },
  {
    sigla: 'BA',
    nome: 'Bahia'
  },
  {
    sigla: 'CE',
    nome: 'Ceará'
  },
  {
    sigla: 'DF',
    nome: 'Distrito Federal'
  },
  {
    sigla: 'ES',
    nome: 'Espírito Santo'
  },
  {
    sigla: 'GO',
    nome: 'Goiás'
  },
  {
    sigla: 'MA',
    nome: 'Maranhão'
  },
  {
    sigla: 'MT',
    nome: 'Mato Grosso'
  },
  {
    sigla: 'MG',
    nome: 'Minas Gerais'
  },
  {
    sigla: 'PA',
    nome: 'Pará'
  },
  {
    sigla: 'PB',
    nome: 'Paraíba'
  },
  {
    sigla: 'PR',
    nome: 'Paraná'
  },
  {
    sigla: 'PE',
    nome: 'Pernambuco'
  },
  {
    sigla: 'PI',
    nome: 'Piuaí'
  },
  {
    sigla: 'RJ',
    nome: 'Rio de Janeiro'
  },
  {
    sigla: 'RN',
    nome: 'Rio Grande do Norte'
  },
  {
    sigla: 'RS',
    nome: 'Rio Grande do Sul'
  },
  {
    sigla: 'RO',
    nome: 'Rondônia'
  },
  {
    sigla: 'RR',
    nome: 'Roraima'
  },
  {
    sigla: 'SC',
    nome: 'Santa Catarina'
  },
  {
    sigla: 'SP',
    nome: 'São Paulo'
  },
  {
    sigla: 'SE',
    nome: 'Sergipe'
  },
  {
    sigla: 'TO',
    nome: 'Tocantins'
  }
]
const linguagensprog = [
  {
    nome: 'Python'
  },
  {
    nome: 'JavaScript'
  },
  {
    nome: 'C++'
  },
  {
    nome: 'Java'
  },
  {
    nome: 'PHP'
  }
]

function salvar() {
  if (form.nome === '' || form.email === '' || form.senha == '') {
    alert('Os campos nome, e-mail e senha são obrigatórios')
  }
  emit('adicionar', form)
}
</script>
<template>
  <form @submit.prevent="salvar">
    <div>
      <label for="nome">Nome</label>
      <input type="text" id="nome" v-model="form.nome" />
    </div>
    <div>
      <label for="email">E-mail</label>
      <input type="email" id="email" v-model="form.email" />
    </div>
    <div>
      <label for="senha">Senha</label>
      <input type="password" id="senha" v-model="form.senha" />
    </div>
    <div>
      <label for="confisenha">Confirmação de senha</label>
      <input type="password" id="confisenha" v-model="form.confisenha" />
    </div>
    <div>
      <label for="datanasc">Data de nascimento</label>
      <input type="date" id="data" v-model="form.datanasc" />
    </div>
    <div>
      <label for="endereco">Endereço</label>
      <input type="text" id="enderco" v-model="form.endereco" />
    </div>
    <div>
      <label for="cidade">Cidade</label>
      <input type="text" id="cidade" v-model="form.cidade" />
    </div>
    <div>
      <label for="form.estado">Estado:</label>
      <select v-model="form.estado">
        <option value="" disabled>Selecione um estado</option>
        <option v-for="estado in estados" :key="estado.sigla" :value="estado.nome">
          ({{ estado.sigla }}) {{ estado.nome }}
        </option>
      </select>
    </div>
    <label for="hobbies">Hobbies</label>
    <input type="text" id="hobbies" v-model="form.hobbies" />
    <div>
      <fieldset>
        <legend>Linguagem de programação:</legend>
        <!-- arrumar o checkbox, um clique esta selecionando todos -->
        <template v-for="linguagem in linguagensprog" :key="linguagem.nome">
          <input v-model="form.linguagemprog" :value="linguagem.nome" type="checkbox" />
          {{ linguagem.nome }}
        </template>
      </fieldset>
      <label for="bio">Biografia</label>
      <input type="text" id="bio" v-model="form.bio" />
    </div>
    <button type="submit">Salvar</button>
  </form>
</template>
