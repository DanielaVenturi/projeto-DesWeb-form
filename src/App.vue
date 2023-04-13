<script setup>
import { ref } from 'vue'
const nome = ref('')
const email = ref('')
const senha = ref('')
const rua = ref('')
const bairro = ref('')
const data = ref('')
const estados = ref('')
const hobies = ref('')
const bio = ref('')
const lingPro = ref('')
const enviar = ref(false)
const senhaConf = ref('')
</script>

<template>
  <div class="conteudo">

<div class="tudo informacoes">

  <form @submit.prevent='enviar = !enviar'>

<h1>Login</h1>
<div>
  <p>Nome</p>

  <input type="text" v-model="nome" placeholder="Digite seu nome" required />

</div>

<div>
  <p>Email</p>
  <input type="email" v-model="email" placeholder="Digite um E-mail" required />
  
</div>

<div>
  <p>Senha</p>
  <input type="password" v-model="senha" placeholder="Digite uma senha" required>
  <br>
  <input type="password" v-model="senhaConf" placeholder="Confirme sua senha" required>
</div>

<div>
  <p>Data de nascimento</p>
  <input type="date" v-model="data" required>
</div>

<div>
  <p>Endereço</p>
  <input type="text" v-model="rua" placeholder="Rua" required>
  <input type="text" v-model="bairro" placeholder="Bairro" required>
  <br>
  <select v-model="estados">
    <option value="">Estado</option>
    <option value="Acre">AC</option>
    <option value="Alagoas">AL</option>
    <option value="Amapa">AP</option>
    <option value="Amazonas">AM</option>
    <option value="Bahia">BA</option>
    <option value="Ceara">CE</option>
    <option value="Distrito Federal">DF</option>
    <option value="Espirito Santo">ES</option>
    <option value="Goiania">GO</option>
    <option value="Maranhao">MA</option>
    <option value="Mato grosso">MT</option>
    <option value="Mato gosso do sul">MS</option>
    <option value="Minas gerais">MG</option>
    <option value="Para">PA</option>
    <option value="Paraiba">PB</option>
    <option value="Parana">PR</option>
    <option value="Pernambuco">PE</option>
    <option value="Piaui">PI</option>
    <option value="Rio de Janeiro">RJ</option>
    <option value="Rio grande do Norte">RN</option>
    <option value="Rio grande do sul">RS</option>
    <option value="Rondonia">RO</option>
    <option value="Roraima">RR</option>
    <option value="Santa Catarina">SC</option>
    <option value="Sao paulo">SP</option>
    <option value="Sergipe">SE</option>
    <option value="Tocantins">TO</option>
  </select>
  <input type="text" placeholder="Digite o nome da sua Cidade" required>

</div>
<div>
  <p>Sobre Você</p>
  <input type="text" v-model="hobies" placeholder="Digite um dos seus Hobbies" required maxlength="25"
    minlength="10">

  <input type="text" v-model="bio" placeholder="Biografia curta" required maxlength="51" minlength="10">

  <select v-model="lingPro">
    <option value="">Linguagem De Programação</option>
    <option value="JavaScript">JS</option>
    <option value="Java">Java</option>
    <option value="Python">Python</option>
    <option value="PHP">PHP</option>
    <option value="C++">C++</option>
    <option value="C#">C#</option>
    <option value="TypeScript">TypeScript</option>
    <option value="Ruby">Ruby</option>
  </select>
</div>
<br>
<button type='submit' class="btn btn-outline-primary" >Cadastrar</button>
</form>

</div>

<div v-if="enviar">

  <div class="tudo enviar">

<div> Nome:   {{ nome }}</div>
<div> Email:{{ email }}</div>
<div>Senha:  {{ senha }}</div>
<div>Senha Confirmada: {{ senhaConf }}</div>
<div>Data: {{ data }}</div> 
<div>Rua: {{ rua }} </div>
<div>Bairro: {{ bairro }}</div>
<div>Estado: {{ estados }} </div>
<div>Hobbies: {{ hobies }}</div>
<div>Bio: {{ bio }}</div>
<div> Linguagem de Programação : {{ lingPro }}</div>

  </div>

</div>

</div>
</template>

<style scoped>
.conteudo{
  color: #fff;
  text-align: center;
  
}


.tudo{
  background-color: darkgrey;
  border-style: outset;
  
  width: 400px;
  
}
.informacoes{

}

.enviar{
font-weight: bold;
}
</style>
