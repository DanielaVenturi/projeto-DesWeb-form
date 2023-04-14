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
const user = ref({
  avatar: null
})

function handleFileUpload(e) {
  const target = e.target
  if (target && target.files) {
    const file = target.files[0]
    user.value.avatar = URL.createObjectURL(file)
  }
}


</script>

<template>
  <div class="container">

    <div class="box">

      <form @submit.prevent='enviar = !enviar'>

        <h1>Login</h1>
        <hr>
        <label for="nome">Nome:</label>
        <div class="margin">
          

          <input name="nome" type="text" v-model="nome" placeholder="Digite seu nome" required />
          <hr>

        </div>
        <label for="email">e-Mail:</label>
        <div class="margin">
          
          
          <input name="email" type="email" v-model="email" placeholder="Digite um E-mail" required />
          <hr>

        </div>
        <label for="senha">Senha:</label>
        <div class="margin">
          
          <input neme="senha" type="password" v-model="senha" placeholder="Digite uma senha" required>
          <br>
          <input name="senha" type="password" v-model="senhaConf" placeholder="Confirme sua senha" required>
          <hr>
        </div>
        <label for="data">Data de Nascimento</label>
        <div class="margin">
          
          <input name="data" type="date" v-model="data" required>
          <hr>
        </div>
        <label for="endereco">Endereço</label>
        <div class="margin">
         
          <input name="endereco" type="text" v-model="rua" placeholder="Digite o Nome da Rua" required><br>
          <input  name="endereco" type="text" v-model="bairro" placeholder="Digite o Nome da Bairro" required><br>
          
          
          <input name="endereco" type="text" placeholder="Digite o nome da sua Cidade" required><br>

          <select name="endereco" v-model="estados">
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
<hr>
        </div>
        <label for="bio">Um Pouco Sobre Você</label>
        <div class="margin">
          
          <input name="bio" type="text" v-model="hobies" placeholder="Digite um dos seus Hobbies" required maxlength="25"
            minlength="10"><br>

          <input name="bio" type="text" v-model="bio" placeholder="Biografia curta" required maxlength="51" minlength="10"><br>

          

          <select neme="bio" v-model="lingPro">
            <option value="">Linguagem De Programação</option>
            <option value="JavaScript">JS</option>
            <option value="Java">Java</option>
            <option value="Python">Python</option>
            <option value="PHP">PHP</option>
            <option value="C++">C++</option>
            <option value="C#">C#</option>
            <option value="TypeScript">TypeScript</option>
            <option value="Ruby">Ruby</option>
          </select><br>
          <hr>
<label for="avatarField">Foto de Perfil</label>
<div class="margin">
  <input
    type="file"
    id="avatarField"
    @change="handleFileUpload($event)"
/>
</div>
         
          
        </div>
        <br>
        <hr>
        <button type='submit' class="btn btn-outline-primary">Cadastrar</button>
      </form>

    </div>

    <div class="box" v-if="enviar">

     
        <div>
          <h1>Login</h1>
          <hr>
<div class="margin"><label for="nome">Nome:</label>
           {{ nome }}</div>
          </div>
           <hr>
        <div class="margin"> 
          <label for="email">E-mail:</label>
          {{ email }}</div>
          <hr>
        <div  class="margin">
          <label for="senha">Senha:</label>
          {{ senha }}</div>
        <div  class="margin">
          <label for="senha">Senha confirmada:</label>
           {{ senhaConf }}</div>
        <div class="margin">
          <hr>
          <h3>Data de Nascimento</h3>
          
        </div>
        <div  class="margin">
          <label for="data">Data:</label>
          {{ data }}</div> <hr>
        <div class="margin">
          <h3>Endereço</h3>
        </div>
        <div  class="margin">
          <label for="rua">Rua:</label>
          {{ rua }} </div>
        <div  class="margin">
          <label for="nome">Bairro:</label>
          {{ bairro }}</div>
        <div  class="margin">
          <label for="Estado">Estado:</label>
          {{ estados }} </div>
          <hr>
        <div class="margin">
          <h3>Hobbies</h3>
        </div>
        <div  class="margin">
          <label for="hobie">Hobie:</label>
          {{ hobies }}</div>
        <div  class="margin">
          <label for="bio">Biografia:</label>
          {{ bio }}</div>
        <div  class="margin">
          <label for="lingPro">Linguagem Programação:</label>
          {{ lingPro }}</div>
          <hr>
          <h3>Foto de Perfil</h3>
        <div class="margin">
          
          <img :src="user.avatar" />
        </div>

        
     

    </div>

  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: row;
  justify-content: center;
  background-color: rgb(152, 41, 221);
  border-style: outset;
  border-color: rgb(213, 111, 253);
  height: 965px;
  width: 800px;
  margin: 0 auto;
  margin-top: 150px;
  
}

.box {
 text-align: center;
 border-style: outset;
  height: 965px;
  width: 800px;
  margin: 0 auto;
  border-color: rgb(140, 127, 255);
}

.margin{margin-top: 10px;
margin-bottom: 10px;
color: aliceblue;
}
label{
  font-size: 20px;
  font-weight: bold;
  color: rgb(255, 255, 255);
}
input{
  font-size: 18px;
  font-weight: 300;
  border-radius: 10px;
  border: 1px solid;
  background-color: rgba(183, 139, 238, 0.581);
}
select{
  font-size: 18px;
  font-weight: 300;
  border-radius: 10px;
  border: 1px solid;
  background-color: rgba(183, 139, 238, 0.581);
}
img{
  width: 100px;
  height: 100px;
  border-radius: 50px;
  border: 2px solid;
}
h1{
  font-size: 40px;
  font-weight: bold;
  margin-top: 10px;
  color: rgb(249, 249, 249);
}
h3{
  font-size: 30px;
  font-weight: bolder;
  margin-top: 10px;
  color:  rgb(255, 255, 255);
}
button{
  font-size: 30px;
  font-weight: 400;
  border-radius: 10px;
  border: 1px solid;
  background-color: rgba(178, 86, 240, 0.581);
  color: rgb(255, 255, 255);
  margin-top: 30px;

}




</style>
