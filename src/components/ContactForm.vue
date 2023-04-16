<script setup>
    import SendIcon from './icons/SendIcon.vue'
    import CheckIcon from './icons/CheckIcon.vue'
    import ArrowBackIcon from './icons/ArrowBackIcon.vue'
</script>

<template>
    <section class="contact-form d-none">
        <div class="contact-form__container page-width">
            <h2>Send me an E-mail!</h2>

            <form action="https://formsubmit.co/ajax/serragonzalo1@gmail.com" method="POST" class="contact-form__form">
                <input type="text" name="name" placeholder="Name" pattern="^[A-Za-zÑñÁáÉéÍíÓóÚúÜü\s]+$" required>
                <input type="email" name="email" placeholder="E-mail" pattern="^[a-z0-9]+(\.[_a-z0-9]+)*@[a-z0-9-]+(\.[a-z0-9-]+)*(\.[a-z]{2,15})$" required>
                
                <input type="textarea" name="message" placeholder="Message">
                
                <button type="submit" @click="sendEmail">
                    <span>Send</span>
                    <SendIcon />
                </button>
            </form>

            <button class="back-button" @click="backToHome">
                <span>Back</span>
                <ArrowBackIcon />
            </button>
        </div>
        <div class="contact-form__check">
            <CheckIcon />
            <p class="thanks">Thank you!</p>
            <p class="successfully">The email was sent successfully!</p>
        </div>
    </section>
</template>

<script>
    export default {
        methods: {
            backToHome() {
                let form = document.querySelector('.contact-form')
                form.style.top = '100%'
                
                setTimeout(() => {
                    form.classList.add('d-none')
                    form.removeAttribute('style')
                }, 500)
            },

            sendEmail() {
                const form = document.querySelector(".contact-form__form");
                const sendIcon = document.querySelector(".send-icon");
                const check = document.querySelector(".contact-form__check");
            
                form.addEventListener("submit", async event => {
                    event.preventDefault();
                    sendIcon.style.transform = 'translateX(0)';
                    sendIcon.style.opacity = '1';

                    try {
                        let response = await fetch("https://formsubmit.co/ajax/serragonzalo1@gmail.com", {
                            method: "POST",
                            body: new FormData(event.target)
                        })
                        //let json = await response.json()

                        if(!response.ok) throw { status: response.status, statusText: response.statusText }

                        sendIcon.style.transition = 'all 800ms ease'
                        sendIcon.style.transform = 'translateX(50vw)'
                        
                        setTimeout(() => {
                            check.style.clipPath = 'inset(0)'
                            check.style.borderRadius = '0'

                            sendIcon.style.transition = 'all 300ms ease'
                            sendIcon.style.transform = 'translateX(-40px)'
                            sendIcon.style.opacity = '0';

                            setTimeout(() => {
                                check.style.clipPath = 'inset(100% 0 0 0)'

                                setTimeout(() => {
                                    check.style.clipPath = 'inset(66% 0 34% 100%)'
                                    check.style.borderRadius = '999px'

                                    sendIcon.removeAttribute('style')
                                }, 2900)
                            }, 2600)
                        }, 600)

                    } catch (error) {
                        console.error(error.status, error.statusText)

                        //...
                    }
                })
            }
        }
    }
</script>

<style lang="scss">
    .contact-form {
        position: fixed;
        top: 0;
        left: 0;
        width: 100vw;
        height: 100vh;
        background-color: var(--main-color);
        color: #fff;
        display: flex;
        align-items: center;
        justify-content: center;
        transition: all 300ms ease;
        animation: showContactPage 2000ms ease;

        &__container {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            gap: 20px;
            width: 100%;
            height: 100%;
            position: relative;

            form {
                display: flex;
                flex-direction: column;
                justify-content: center;
                align-items: center;
                gap: 20px;
                border: 2px solid #fff;
                border-radius: 20px;
                padding: 60px;
                animation: showContactForm 1500ms ease;
                background-color: var(--main-color);
            }

            input {
                border: none;
                outline: none;
                height: 48px;
                width: 350px;
                border-radius: 10px;
                padding: 0 20px;
                color: var(--text-color);
            }

            form button {
                border: 2px solid #fff;
                background: transparent;
                color: #fff;
                width: 100%;
                margin-top: 20px;

                svg {
                    fill: #fff;
                    height: 32px;
                    position: absolute;
                    top: 0;
                    bottom: 0;
                    right: 20px;
                    margin: auto 0;
                    transform: translateX(-40px);
                    opacity: 0;
                    transition: all 300ms ease;
                }
            }

            button:hover {
                svg {
                    transform: translateX(0px);
                    opacity: 1;
                }
            }

            h2 {
                font-family: "Raleway";
                animation: showContactFormTitle 2500ms ease;
            }

            .back-button {
                position: absolute;
                bottom: 20px;
                left: 0;
                border: 2px solid #fff;
                background: transparent;
                color: #fff;
                width: 150px;
                font-weight: normal;
                transition: all 300ms ease;
                opacity: .7;

                svg {
                    position: absolute;
                    top: 0;
                    bottom: 0;
                    margin: auto 0;
                    left: 10px;
                    transform: translateX(25px);
                    opacity: 0;
                    transition: all 300ms ease;
                }
            }

            .back-button:hover {
                opacity: 1;

                svg {
                    opacity: 1;
                    transform: translateX(0);
                }
            }
        }

        &__check {
            position: absolute;
            right: 0;
            top: 0;
            width: 100vw;
            height: 100vh;
            background: #00b51b;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            gap: 30px;
            transition: all 300ms ease;
            clip-path: inset(66% 0 34% 100%);
            border-radius: 999px;

            .thanks {
                font-size: 2rem;
                font-weight: bold;
            }

            .successfully {
                font-size: 1.3rem;
            }
        }
    }

    @keyframes showContactPage {
        0% {
            top: 100vh;
            background-color: var(--second-color);
        }
        50% {
            top: 0;
            background-color: var(--second-color);
        }
        100% {
            top: 0;
            background-color: var(--main-color);
        }
    }

    @keyframes showContactForm {
        0% {
            padding: 100vh 100vw;
            opacity: 0;
        }
        20% {
            padding: 100vh 100vw;
            opacity: 1;
        }
        100% {
            padding: 60px;
            opacity: 1;
        }
    }

    @keyframes showContactFormTitle {
        0% {
            transform: translateY(100px);
            opacity: 0;
        }
        60% {
            transform: translateY(100px);
            opacity: 0;
        }
        100% {
            transform: translateY(0);
            opacity: 1;
        }
    }
</style>