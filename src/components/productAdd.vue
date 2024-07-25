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
  estado: '',
  hobbies: '',
  lingprog: [],
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
  emit('adicionar', form)
}
</script>
<template class="form">
  <form @submit.prevent="salvar">
    <div class="inputs">
      <div>
        <label for="nome">Nome: </label>
        <input type="text" id="nome" v-model="form.nome" placeholder="Insira seu nome" />
      </div>
      <div>
        <label for="email">E-mail: </label>
        <input type="email" id="email" v-model="form.email" placeholder="Insira seu email" />
      </div>
      <div>
        <label for="senha">Senha: </label>
        <input type="password" id="senha" v-model="form.senha" placeholder="Insira uma senha" />
      </div>
      <div>
        <label for="confisenha">Confirmação de senha: </label>
        <input type="password" id="confisenha" v-model="form.confisenha" placeholder="Confirme sua senha" />
      </div>
      <div>
        <label for="datanasc">Data de nascimento: </label>
        <input type="date" id="datanasc" v-model="form.datanasc" />
      </div>
      <div>
        <label for="endereco">Endereço: </label>
        <input type="text" id="enderco" v-model="form.endereco" placeholder="Insira seu endereçõ" />
      </div>
      <div>
        <label for="cidade">Cidade: </label>
        <input type="text" id="cidade" v-model="form.cidade" placeholder="Insira sua cidade" />
      </div>
      <div>
        <label for="estado">Estado: </label>
        <select v-model="form.estado" id="estado">
          <option value="" disabled>Selecione um estado</option>
          <option v-for="estado in estados" :key="estado.sigla" :value="estado.nome">
            ({{ estado.sigla }}) {{ estado.nome }}
          </option>
        </select>
      </div>
      <label for="hobbies">Hobbies: </label>
      <input type="text" id="hobbies" v-model="form.hobbies" placeholder="Insira seu(s) hobbie(s)" />
      <div>
        <label for="lingprog">Linguagens de programação: </label>
        <fieldset>
          <!-- arrumar o checkbox, um clique esta selecionando todos -->
          <template v-for="linguagem in linguagensprog" :key="linguagem.nome">
            <label>
              <input v-model="form.lingprog" :value="linguagem.nome" type="checkbox" />
              {{ linguagem.nome }}
            </label>
          </template>
        </fieldset>
      </div>
      <div>
        <label for="bio">Biografia: </label>
        <input type="text" id="bio" v-model="form.bio" placeholder="Escreva uma mini biografia" />
      </div>
      <button type="submit">Salvar</button>
    </div>
  </form>
</template>

<style scoped>
button{
  display: flex;
  justify-content: start;
  margin-left: 2%;
  background-color: palevioletred;
}
form {
   /*opaaaaaaaa*/
}

input{
  display: flex;
  justify-content: start;
  margin-left: 2%;

}

label{
  display: flex;
  justify-content: left;
  margin-top: 2%;
  margin-left: 2%;
}


</style>
