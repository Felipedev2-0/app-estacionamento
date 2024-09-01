<template>

    <div class="mensagem-container">

    <!-- mensagem sendo passada de forma dinamica com props-->
        <h2>{{ msg }}</h2>

    </div>
  
</template>

<script>
export default {
    name: "Mensagem",

    props: {
        msg: String
    }
    
}
</script>

<style scoped>

    .mensagem-container{
        color: white;
        background-color: #008055 ;
        border: 2px solid #b8daff;
        border-radius: 10px;
        padding: 10px;
        max-width: 400px;
        margin: 30px auto;
    }




</style>