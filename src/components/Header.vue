<script setup>

import { ref } from 'vue';

const activeMenuItem = ref('');

function addLine(item) {
    activeMenuItem.value = item;
}

</script>


<template>
    <header>
        <div class="container">
            <a href="#" :class="{ 'active': activeMenuItem === 'Accueil' }">
                <img class="logo-portfolio" src="../assets/images/barista.png" alt="Logo Portfolio" @click="() => addLine('Accueil')">
            </a>

            <h1>Abdelouahid BOUZIANE</h1>

            <nav>
                <ul class="list">
                    <li :class="{ 'active': activeMenuItem === 'Accueil' }">
                        <a href="#" class="link" @click="() => addLine('Accueil')">Accueil</a>
                    </li>
                    <li :class="{ 'active': activeMenuItem === 'About' }">
                        <a href="#about" class="link" @click="() => addLine('About')">About</a>
                    </li>
                    <li :class="{ 'active': activeMenuItem === 'Projets' }">
                        <a href="#projects" class="link" @click="() => addLine('Projets')">Projets</a>
                    </li>
                    <li :class="{ 'active': activeMenuItem === 'Contact' }">
                        <a href="#contact" class="link" @click="() => addLine('Contact')">Contact</a>
                    </li>
                </ul>
            </nav>

        </div>
    </header>
</template>


<style scoped>

header {
    background-color: #019ca1;
    color: #ecf0f1;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 100;
    padding: 15px 0;
}
header .container{
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.logo-portfolio{ 
    width: 100;
    height: 100px;
    border-radius: 50%;
    box-shadow: 0 0 30px  rgb(2, 253, 253);
}

header h1 {
    margin: 0;
    font-size: 2em;
    
}

/* NAVBAR */
nav ul {
    list-style: none;
    display: flex;
    margin: 0;
    padding: 0;
}

nav li {
    margin-right: 30px;
}

nav li a {
    text-transform: uppercase;
    text-decoration: none;
    font-weight: 600;
    letter-spacing: 0.11em;
    color: #ecf0f1;
    font-size: 1.2em;
}

nav li a:after {
  content: '';
  display: block;
  margin: auto;
  height: 10%;
  width: 0;
  background: transparent;
  transition: width .5s ease, background-color .5s ease;
}

nav li a:hover:after {
  width: 90%;
  background: #eca7a7;
}

.list li.active {
    text-decoration: underline;
    color: #eca7a7;
    
}

</style>
