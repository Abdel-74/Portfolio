<script setup>
import { RouterLink, RouterView} from 'vue-router'
import Header from '../components/Header.vue'
import Footer from '../components/Footer.vue'

</script>


<template>
    <RouterView>
        <main class="container">
                <Header></Header>
                    <div class="logo">
                        <img src="../assets/images/error-404.png" alt="Image erreur 404" class="logo">
                    </div>
                    <h1>Page Not Found</h1>
                    
                <RouterLink class="home" to="/">Retourner à la page d'acceuil</RouterLink>
        </main>
        <Footer></Footer>
    </RouterView>
</template>

<style scoped>

.logo{
    display: flex;
    justify-content: center;
    margin: 50px;
    margin-bottom: 0;
}
.logo:hover{
    opacity: 0.8;
}

h1{
    display: flex;
    justify-content: center;
    background-color: rgb(102, 156, 238);
    width: 400px;
    margin-left: 35%;
}

.home{
    text-decoration: none;
    color: rgb(199, 110, 8);
    font-weight: 700;
    font-size: 25px;
    animation: 1s anim-home ease infinite;
} 

@keyframes anim-home {
    0% {
        opacity: 0;
    }
    100% {
        opacity: 1;
    }
}

.home:hover{
    background-color:transparent;
    color:#ff0909;
}

</style>
