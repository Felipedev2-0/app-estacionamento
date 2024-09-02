<template>

    <div>

        <!--chamando component mensagem-->
        <Mensagem :msg="msg" v-show="msg" />

        <!--criando @submit e metodo createCarro para envio de dados-->
        <form id="carro-form" @submit="createCarro">

            <div class="input-container">

                <label for="nome">Nome da Pessoa: </label>
                <input type="text" id="nome" v-model="nome" placeholder="Informe o seu nome">


            </div>

            <div class="input-container">

                <label for="nome">Nome do Carro: </label>
                <input type="text" id="nomeCarro" v-model="nomeCarro" placeholder="Informe o nome do carro">


            </div>

            <div class="input-container">

                <label for="nome">Placa do Carro: </label>
                <input type="text" id="placaCarro" v-model="placaCarro" placeholder="Informe a placa do carro">


            </div>

            <div class="input-container">

                <label for="hora">Horário de Entrada: </label>
                <input type="text" id="hora" v-model="hora" placeholder="Informe o horário de entrada">


            </div>

            <div>

                <input type="submit" class="submit-btn" value="Cadastrar Carro">


            </div>



        </form>



    </div>


</template>

<script>

import Mensagem from './Mensagem.vue';

export default {
    name: "CarroForm",

    data() {
        return {

            nome: null,
            nomeCarro: null,
            placaCarro: null,
            hora: null,
            msg: null

        }
    },

    methods: {
        async createCarro(e) {

            //para a aplicacao depois de executar
            e.preventDefault();


            const data = {
                nome: this.nome,
                nomeCarro: this.nomeCarro,
                placaCarro: this.placaCarro,
                hora: this.hora,
                msg: this.msg,
                status: "Solicitado",
            }

            //transformar os dados json em string para o backend
            const dataJson = JSON.stringify(data)

            //enviar os dados do form para o arquivo db.json com o POST
            const req = await fetch("http://localhost:3000/carros", {
                method: "POST",
                headers: { "Content-Type": "application/json" },
                body: dataJson
            });

            //OBTENDO A RESPOSTA DO POST
            const res = await req.json()

            
            //METODO PARA CHAMAR A MENSAGEM DE SUCESSO NO CADASTRO
            this.msg=`Carro Cadastrado com Sucesso.`

            //LIMPAR A MENSAGEM APÓS O TEMPO
            setTimeout(() => this.msg="", 3000)


            //LIMPANDO OS CAMPOS APÓS CADASTRAR CARRO
            this.nome = "",
                this.nomeCarro = "",
                this.placaCarro = "",
                this.hora = ""

        }
    },

    components: {
        Mensagem
    }

}
</script>

<style scoped>
#carro-form {
    max-width: 300px;
    margin: 0 auto;
}

.input-container {
    display: flex;
    flex-direction: column;
    margin-bottom: 20px;
}

label {
    font-weight: bold;
    margin-bottom: 10px;
    color: #222;
    padding: 5px 10px;
    border-left: 4px solid #3f7fbf;
}

input {
    padding: 5px 10px;
    width: 300px;
}

.submit-btn {
    background-color: #3f7fbf;
    color: white;
    font-weight: bold;
    padding: 10px;
    font-size: 16px;
    border: 2px solid white;
    border-radius: 8px;
    cursor: pointer;
    transition: .5s;
}

.submit-btn:hover {
    background-color: tomato;
    font-size: 18px;
    transition: all;
}
</style>