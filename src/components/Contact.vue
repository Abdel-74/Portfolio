<script>
import emailjs from 'emailjs-com';

export default {
    name: 'Contact',
    data() {
        return {
            firstName: '',
            lastName: '',
            email: '',
            message: '',
            showMessage: false
        };
    },
    methods: {
    
        messageSent() {
            this.showMessage = false;
        },
        sendEmail() {
            try {
                emailjs.send('service_ym7f2g5', 'template_7guwvnx', {
                    firstName: this.firstName,
                    lastName: this.lastName,
                    email: this.email,
                    message: this.message
                    },'WO1Qsz2BetVXiaDEt');

                this.showMessage = true,
                setTimeout(this.messageSent, 3000);

            } catch(error) {
                console.log('Erreur lors de l\'envoi de l\'e-mail :', error);
            }
            this.firstName = '',
            this.lastName = '',
            this.email = '',
            this.message = ''
        },
    }
};

</script>

<template>
    
    <section id="contact">
        <h2>Contact</h2>
        <form action="#" @submit.prevent="sendEmail">
            <label for="firstName">Prénom:</label>
            <input v-model="firstName" type="text" id="firstName" name="firstName" required>
            
            <label for="lastName">Nom:</label>
            <input v-model="lastName" type="text" id="lastName" name="lastName" required>
            
            <label for="email">Email:</label>
            <input v-model="email" type="email" id="email" name="email" required>
        
            <label for="message">Message:</label>
            <textarea v-model="message" id="message" name="message" rows="4" required></textarea>
    
            <button type="submit">Submit</button>

            <p  class="messageSent" v-if="showMessage">Message envoyé!</p>
        </form>
    </section>

</template>


<style scoped>

form {
    max-width: 500px;
    margin: 0 auto;
}

label {
    display: flex;
    margin-bottom: 8px;
}

#lastName, #firstName{
    width: 60%;
}

input,
textarea {
    width: 100%;
    padding: 8px;
    margin-bottom: 16px;
    box-sizing: border-box;
    
}

button {
    background-color: #4caf50;
    color: white;
    padding: 10px 15px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

button:hover {
    background-color: #45a049;
}

.messageSent{
    background-color: #1cb64f;
    color : black;
    font-weight: 300;
    font-size: 20px;
    margin-left: 28%;
    width: 300px;
    height: 40px;
    text-align: center;
    
}
</style>
