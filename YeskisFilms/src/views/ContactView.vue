<template>
    <!-- En espanol -->
    <div class="contact" id="contact" v-if="this.lang === 'Es'">
        <h3 class="c-title">Gustas calaborar en un proyecto? Manda me un mensaje!</h3>

        <div class="c">
            <div class="c-info">
                <div class="c-info-item">
                    <img src="../assests/email.png" alt="email icon" />
                    fernandocruz@gmail.com
                </div>

                <div class="c-info-item">
                    <img src="../assests/location.png" alt="location icon" />
                    Arandas, Jalisco
                </div>

                <div class="c-info-item">
                    <img src="../assests/whatsapp.png" alt="whatsapp icon" />
                    +52 348-465-5776
                </div>
            </div>

            <form class="c-form" ref="form" @submit.prevent="sendEmail" v-if="sent === false">
                <input type="text" name="user_name" placeholder="Nombre" />

                <input type="text" name="user_email" placeholder="Correo" />

                <textarea name="message" placeholder="Mensaje"></textarea>

                <button class="c-submit" type="submit" value="Send" v-on:click="sent = true">Enviar</button>
            </form>

            <p class="success" v-if="sent === true">Gracias! Pronto estare en contacto!</p>
        </div>
    </div>

    <!-- In english -->
    <div class="contact" id="contact" v-if="this.lang === 'En'">
        <h3 class="c-title">Want to collaborate? Get in touch!</h3>

        <div class="c">
            <div class="c-info">
                <div class="c-info-item">
                    <img src="../assests/email.png" alt="email icon" />
                    fernandocruz@gmail.com
                </div>

                <div class="c-info-item">
                    <img src="../assests/location.png" alt="location icon" />
                    Arandas, Jalisco
                </div>

                <div class="c-info-item">
                    <img src="../assests/whatsapp.png" alt="whatsapp icon" />
                    +52 348-465-5776
                </div>
            </div>

            <form class="c-form" ref="form" @submit.prevent="sendEmail" v-if="sent === false">
                <input type="text" name="user_name" placeholder="Name" />

                <input type="text" name="user_email" placeholder="Email" />

                <textarea name="message" placeholder="Message"></textarea>

                <button class="c-submit" type="submit" value="Send" v-on:click="sent = true">Send</button>
            </form>

            <p class="success" v-if="sent === true">Thanks! Ill get back in touch soon!</p>
        </div>
    </div>
</template>

<script>
import emailjs from '@emailjs/browser';

export default {
    data() {
        return {
            sent: false
        }
    },
    props: ['lang'],
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
    justify-content: space-evenly;
    align-items: center;
}

.c {
    display: flex;
    justify-content: center;
    align-items: flex-start;
}

.c-title {
    font-style: italic;
    font-weight: 800;
}

.c-form {
    width: 30rem;
    height: 40vh;
    display: flex;
    flex-direction: column;
    padding: 0 3rem;
    margin: 0 3rem;
    justify-content: space-between;
    
}

.c-form input {
    width: 50%;
    height: 50px;
    border: none;
    margin: 10px 0px;
    font-size: 14px;
    padding-left: 10px;
    border: 1px solid black;
    border-radius: 3px;
}

.c-form textarea {
    width: 100%;
    height: 10rem;
    margin: 10px 0px;
    font-size: 14px;
    padding-left: 10px;
}


.c-submit {
    all: unset;
    width: 100px;
    height: 30px;
    font-size: 16px;
    background: transparent;
    border: none;
    position: relative;
    color: black;
    cursor: pointer;
    z-index: 1;
    padding: 10px 20px;
    display: flex;
    align-items: center;
    justify-content: center;
    white-space: nowrap;
    user-select: none;
    -webkit-user-select: none;
    touch-action: manipulation;
    font-weight: 500;
}

.c-submit::after,
.c-submit::before {
    content: '';
    position: absolute;
    bottom: 0;
    right: 0;
    z-index: -99999;
    transition: all .4s;
}

.c-submit::before {
    transform: translate(0%, 0%);
    width: 100%;
    height: 100%;
    background: #FB3640;
    border-radius: 10px;
}

.c-submit::after {
    transform: translate(10px, 10px);
    width: 35px;
    height: 35px;
    background: #ffffff15;
    backdrop-filter: blur(5px);
    -webkit-backdrop-filter: blur(5px);
    border-radius: 50px;
}

.c-submit:hover::before {
    transform: translate(5%, 20%);
    width: 110%;
    height: 110%;
}

.c-submit:hover::after {
    border-radius: 10px;
    transform: translate(0, 0);
    width: 100%;
    height: 100%;
}

.c-submit:active::after {
    transition: 0s;
    transform: translate(0, 5%);
}

.c-info-item {
    display: flex;
    justify-content: flex-start;
    align-items: center;
    padding: 0 3rem;
    margin: 1rem 0;
}

.c-info-item img {
    height: 2rem;
    padding-right: 1rem;
}

.c-info-item img:hover {
    transform: scale(1.3);
    transition: ease-in 0.5s;
}

@media (max-width:992px) {
    .contact {
        margin: 15rem;
        flex-direction: column;
    }

    .c {
        flex-direction: column-reverse;
        justify-content: space-evenly;
        align-items: center;
    }

    .c-title {
        justify-content: center;
        text-align: center;
        width: 15em;
        font-weight: 600;
    }

    .c-form {
        width: auto;
        height: auto;
        justify-content: center;
        align-items: center;
        margin-bottom: 4rem;
    }

    .c-form input {
        width: auto;
    }

    .c-form textarea {
        width: auto;
        height: 5rem;
    }

}
</style>