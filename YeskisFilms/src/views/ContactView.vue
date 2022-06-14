<template>
    <div class="contact">
        <h3>Want to collaborate? Get in touch!</h3>

        <form class="col" ref="form" @submit.prevent="sendEmail">
            <input class="effect" type="text" placeholder="Name">
            <span class="focus-border"></span>
            <label>Email</label>
            <input type="email" name="user_email">
            <label>Message</label>
            <textarea name="message"></textarea>
            <input type="submit" value="Send">
        </form>
    </div>
</template>

<script>
import emailjs from '@emailjs/browser';

export default {
    methods: {
        sendEmail() {
            emailjs.sendForm('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', this.$refs.form, 'YOUR_PUBLIC_KEY')
                .then((result) => {
                    console.log('SUCCESS!', result.text);
                }, (error) => {
                    console.log('FAILED...', error.text);
                });
        }
    }
}
</script>

<style>
.contact {
    width: auto;
    height: 90vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

h3 {
    color: white;
}

input[type="text"] {
    font: 15px/24px 'Muli', sans-serif;
    color: #333;
    width: 100%;
    box-sizing: border-box;
    letter-spacing: 1px;
}

.col-3 {
    float: left;
    width: 27.33%;
    margin: 40px 3%;
    position: relative;
}

:focus {
    outline: none;
}

input[type="text"] {
    font: 15px/24px "Lato", Arial, sans-serif;
    color: #333;
    width: 100%;
    box-sizing: border-box;
    letter-spacing: 1px;
}

.effect {
    border: 0;
    padding: 7px 0;
    border-bottom: 1px solid #ccc;
}

.effect~.focus-border {
    bottom: 0;
    left: 0;
    width: 0;
    height: 2px;
    background-color: #4caf50;
    transition: 0.4s;
}

.effect:focus~.focus-border {
    width: 100%;
    transition: 0.4s;
}
</style>