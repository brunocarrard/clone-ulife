<script setup lang="ts">
import { ref } from 'vue'
    let popError = ref(false);
    let popSuccess = ref(false);
    let logedName = ref("");
    const accounts = [{
        name: "Bruno Carrard",
        login: "bruno",
        senha: "123"
    }, {
        name: "Marlon Burnnet",
        login: "marlon",
        senha: "123"
    }];
    let loginInput = ref("");
    let senhaInput = ref("");
    const validateLogin = () => {
       if (accounts.find(account => account.login == loginInput.value)?.senha == senhaInput.value) {
        popError.value = false;
        popSuccess.value = true;
        logedName.value = accounts.find(account => account.login == loginInput.value)?.name!
       } else {
        popError.value = true;
        popSuccess.value = false;
       }
    }

</script>

<template>
<div class="main column p-0">
    <div class="context m-0">
        <h1>Ulife: sua vida acadêmica em um só lugar</h1>
        <div class="icon_box row mt-4">
            <div class="icon_content col-4 text-center " >
                <i class="icon-VirtualMeeting d-block"></i>
                <p class="text-center mt-1 d-none d-lg-block mb-0">Aula Virtual</p>
            </div>
            <div class="icon_content col-4 text-center">
                <i class="icon-Attachment d-block"></i>
                <p class="text-center mt-1 d-none d-lg-block mb-0">Material complementar</p>
            </div>
            <div class="icon_content col-4 text-center">
                <i class="icon-Book d-block mb-1"></i>
                <p class="text-center mt-1 d-none d-lg-block mb-0">Biblioteca</p>
            </div>
        </div>
    </div>
    <div class="login_context column mt-3">
        <p class="mt-2 mb-0 p-0 success" v-if="popSuccess">Bem vindo {{logedName}}!</p>
        <p class="mt-2 mb-0 p-0 error" v-if="popError">Usuário ou senha incorretos.</p>
        <input v-model="loginInput" class="mt-1 p-2" type="text" placeholder="RA ou Login:">
        <input v-model="senhaInput" class="mt-1 p-2" type="password" placeholder="Senha">
        <button class="p-2 mt-1" @click="validateLogin"> ENTRAR</button>
        <p class="mt-2 mb-0 p-0">Estudantes e Educadores: utilizem o mesmo login e a senhas os outros ambientes institucionais.</p>
        <p class="mt-2 p-0 col-12"><a href="" >Esqueci minha senha</a></p>
    </div>
</div>
</template>

<style scoped>
.main {
    width: 270px;
    
}

i {
    width: 100%;
    font-size: 2rem;
}

.success {
    color: green;
}

.error {
    color: red;
}
.context {
    border: 1px, solid, black !important;
}

a {
    width: 100%;
}

button {
    width: 100%;
    font-size: 0.9rem;
}

h1 {
    font-size: 1.2rem;
    text-align: left;
}

input {
    width: 100%;
    font-size: 0.9rem;
}

span {
    font-size: 0.7rem;
    line-height: 0.5rem;
}

p {
    font-size: 0.7rem;
    text-align: left;
}


</style>
