<script setup>

import Header from '../components/Header.vue'
import About from '../components/About.vue'
import Modal from '../components/Modal.vue'
import Contact from '../components/Contact.vue'
import Footer from '../components/Footer.vue'
import { RouterView } from 'vue-router'
import { ref } from 'vue';


const showModalCv = ref(false);
function toggleModalCv() {
    showModalCv.value = !showModalCv.value
};
const showModalComment = ref(false);
function toggleModalComment() {
    showModalComment.value = !showModalComment.value
};
const showModalCc = ref(false);
function toggleModalCc() {
    showModalCc.value = !showModalCc.value
};
</script>

 <script>
export default {
  name: "app",
  components: {
    Modal,
  },
  props: ['selectedProject'],
  data() {
    return {
      projects: [
            {
                id: 1,
                img: "cv_1",
                title: "CV en HTML / CSS",
                date: "10/11/2023",
                technologies: ["HTML", "CSS", "GitHub"],
                link: "https://github.com/Abdel-74/Project_CV"
        
            },
            {
                id: 2,
                img: "commentaire_1",
                title: "Espace de commentaires",
                date: "16/12/2023",
                technologies: ["HTML", "CSS", "Javascript", "GitHub"],
                link: "https://github.com/Abdel-74/DynamiserUnEspaceDeCommentaires"
        
            },
            {
                id: 3,
                img: "cc_1",
                title: "Cahier des charges",
                date: "22/11/2023",
                technologies: "",
                link: "lien pdf de telechargement"
            },
      ],
    };
  },
};
</script>


<template>
<RouterView>
    <main class="container">
        <Header></Header>
        <About></About>
 
            <section id="projects">
                <div class="titre">
                    <h2>Projets</h2>
                </div>
                <div class="project-cv">
                    <div class="project" @click="toggleModalCv">
                        <img src="../assets/images/cv_1.PNG" alt="Photo d'un CV">
                        <h3>CV en HTML / CSS</h3>
                    </div>
                    <div v-if="showModalCv">
                        <Modal @close="toggleModalCv"></Modal>
                    </div>
                </div>

                <div class="project-comment">
                    <div class="project" @click="toggleModalComment">
                        <img src="../assets/images/commentaire_1.PNG" alt="Photo du projet espace de commentaires">
                        <h3>Espace de commentaires</h3>
                    </div>
                    <div v-if="showModalComment" class="modal-comment">
                        <Modal @close="toggleModalComment">
                        <template #title>
                            Espace de commentaires
                        </template>
                        <template #slider>
                            <img class="slides" src="../assets/images/commentaire_1.PNG" alt="Image">
                            <img class="slides" src="../assets/images/commentaire_2.PNG" alt="Image">
                            <img class="slides" src="../assets/images/commentaire_3.PNG" alt="Image">
                        </template>
                        <template #details>
                            <p class="creation-date">Fait le {{ projects[1].date }}</p>
                            <h4>Technologies utilisées:</h4>
                            <ul>
                            <li v-for="technologie in projects[1].technologies">{{ technologie }}</li>
                            </ul>
                            <a href="https://github.com/Abdel-74/DynamiserUnEspaceDeCommentaires" target="_blank"><i class="fa-brands fa-square-github"></i></a> 
                        </template>
                        </Modal>
                    </div>
                </div>

                <div class="project-cc">
                    <div class="project" @click="toggleModalCc">
                        <img src="../assets/images/cc_1.PNG" alt="Photo du projet espace de commentaires">
                        <h3>Cahier des charges</h3>
                    </div>
                    <div v-if="showModalCc" class="modal-cc">
                        <Modal @close="toggleModalCc">
                        <template #title>
                            Cahier des charges
                        </template>
                        <template #slider>
                            <img class="slides" src="../assets/images/cc_1.PNG" alt="Image">
                            <img class="slides" src="../assets/images/cc_2.PNG" alt="Image">
                            <img class="slides" src="../assets/images/cc_3.PNG" alt="Image">
                        </template>
                        <template #details>
                            <p class="creation-date">Fait le {{ projects[2].date }}</p>
                            <a href="../assets/documents/cahier_des_charges.pdf" target="_blank"><i class="fa-solid fa-file-pdf"></i></a> 
                        </template>
                        </Modal>
                    </div>
                </div>
            </section>

        <Contact></Contact>
    </main>
    <Footer></Footer>
</RouterView>
</template>


<style scoped>

section div div{
    margin: 20px 0;
    padding: 30px;
    border-radius: 10px;
    box-shadow: 0 0 15px rgba(0, 0, 0, 0.1);

}


#projects :not(.titre){
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    justify-content: space-between;
}

.project-cv, .project-comment, .project-cc{
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: space-between;
}
.project {
    width:40%; 
    background-color: #fff;
    margin: 10px 0;
    padding: 15px;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    cursor: pointer;
    display: flex;
    flex-direction: column;
    align-items: center;

}

.project h3{
    color: rgb(117, 0, 128);
    display: flex;
    align-content: end;
}
.project img{
    max-width: 100%;  
}

.project:hover{
    box-shadow: 10px 10px 7px rgba(0, 0, 0, 0.2);
}


</style>
