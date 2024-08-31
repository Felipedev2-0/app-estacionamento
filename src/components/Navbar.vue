<template>

    <div id="nav">

        <router-link to="/" id="logo-url">

            <img :src="logo" :alt="alt" id="logo">

        </router-link>


        <router-link to="/">Home</router-link> 
        <router-link to="/cadastro">Cadastro</router-link>
    </div>


</template>

<script>
export default {
    name: "Navbar",
    props:["logo", "alt"] //logo do projeto e imagens
}
</script>

<style scoped>

#nav{
    background-color: #3f7fbf;
    padding: 15px 50px;
    display: flex;
    justify-content: flex-end;
    align-items: center;
}

#nav #logo-url{
    margin: auto ;
    margin-left: 0px;
}

#logo{
    width: 40px;
    height: 40px;
}

#nav a{
    color:white;
    text-decoration: none;
    margin: 12px;
    transition: .5s;
    font-size: 20px;
   
}

#nav a:hover{
    color: rgb(255, 136, 0);
    border-bottom: 2px solid rgb(255, 94, 0);
}



</style>