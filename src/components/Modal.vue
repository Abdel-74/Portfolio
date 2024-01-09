<script setup>

import { defineEmits } from 'vue';

function closeModal(){
    emit('close');
};

const emit = defineEmits();

</script>


<template>
    <div class="bloc-modal">
        <div class="overlay" @click="closeModal"></div>
        <div class="modal">
            <div class="btn-modal" @click="closeModal">X</div>
            <h2>
                <slot name="title">
                    CV en HTML / CSS
                </slot>    
            </h2>

            <div class="slider">
                <slot name="slider">
                    <img class="slides" src="../assets/images/cv_1.PNG" alt="Image">
                    <img class="slides" src="../assets/images/cv_2.PNG" alt="Image">
                    <img class="slides" src="../assets/images/cv_3.PNG" alt="Image">
                </slot>
            </div>   

            <div class="details">
                <slot name="details">
                    <p class="creation-date">Fait le 10/11/2023 </p>
                    <h4>Technologies utilisées:</h4>
                    <ul>
                        <li>HTML</li>
                        <li>CSS</li>
                        <li>Github</li>
                    </ul> 
                    <a href="https://github.com/Abdel-74/Project_CV" target="_blank"><i class="fa-brands fa-square-github"></i></a>                     
                </slot>
            </div>

        </div>
    </div>
</template>


<style>


.bloc-modal{
    position: fixed;
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    
}

.overlay{
    background: rgba(0,0,0,0.5);
    position: fixed;
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
}

.modal {
    background: #f1f1f1;
    color: #333;
    padding: 20px;
    position: fixed;
    margin-top: 130px;
}

.btn-modal{
    color:rgb(255, 255, 255) ;
    background: rgb(223, 106, 106);
    font-weight: 600;
    font-size:large;
    border-radius: 20%;
    width: 20px;
    padding-left: 8px;
    display: flex;
    justify-content: center;
    margin-left: 95%;    
    cursor: pointer;
}

h2, .details p, .details ul{
    margin: 0;
}

.slider {
  width: 100%;
  height: 200px;
  overflow: hidden;
}

.slides {
  width: 300px; 
  height: 200px;
  animation: slide 5s infinite;
}

@keyframes slide {
  from {
    transform: translateX(0);
  }
  30% {
    transform: translateX(0); 
  }
  50% {
    transform: translateX(-100%);
  }
  70%{
    transform: translateX(-100%);
  }
  to {
    transform: translateX(-200%);
  }
}

ul li{
    color: #0e01c5;
    font-weight: bold;
}

.details a{
    margin-top: 20px;
    width: 40px;
    height: 40px;
    text-decoration: none;
    font-size: 40px;
    opacity: 0.8;
}

.details a{
    margin-top: 20px;
    width: 40px;
    height: 40px;
    text-decoration: none;
    font-size: 40px;
    opacity: 0.8;
}
.details a:hover{
    opacity: 0.5;
}

</style>
