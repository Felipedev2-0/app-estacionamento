<template>

    <div :class="['mensagem-container', bgColor]">

    <!-- mensagem sendo passada de forma dinamica com props-->
        <h2>{{ msg }}</h2>

    </div>
  
</template>

<script>
export default {
    name: "Mensagem",

    props: {
        msg: String,
        type: {
            type: String,
            default: 'success' // pode ser success ou error
        }
    },

    computed: {
        bgColor(){
            return this.type === 'error' ? 'bg-red' : 'bg-purple'
        }
    }
    
};
</script>

<style scoped>

    .mensagem-container{
        color: white;
        border: 2px solid #b8daff;
        border-radius: 10px;
        padding: 10px;
        max-width: 400px;
        margin: 30px auto;
    }

    .bg-purple{
        background-color: #8e44ad;
    }

    .bg-red{
        background-color: #e74c3c;
    }






</style>