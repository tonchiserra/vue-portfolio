<template>
    <section class="contact-form d-none">
        <div class="contact-form__container">
            <h2>Send me an E-mail!</h2>
            <form action="#">
                <input type="text">
                <input type="text">
                <input type="textarea">
                <button type="submit"><span>Send</span></button>
            </form>
        </div>
    </section>
</template>

<style>
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
        animation: showContactPage 2000ms ease;
    }

    .contact-form__container {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        gap: 20px;
    }

    .contact-form__container form {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        border: 2px solid #fff;
        border-radius: 20px;
        padding: 60px;
        animation: showContactForm 1500ms ease;
        background-color: var(--main-color);
    }

    .contact-form__container h2 {
        animation: showContactFormTitle 2500ms ease;
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