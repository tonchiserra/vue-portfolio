<script setup>
    import AboutIcon from './icons/AboutIcon.vue'
    import CareerIcon from './icons/CareerIcon.vue'
    import LearningIcon from './icons/LearningIcon.vue'
</script>

<template>
    <section id="About" class="about">
        <div class="section-title page-width">
            <div class="title">
                <div class="title__point"></div>
                <h2 class="title__text">About me</h2>
            </div>
        </div>

        <div class="page-width about__list">
            <div class="about__block">
                <div class="about__block-title">
                    <AboutIcon />
                    <h3>Who am I?</h3>
                </div>
                <div class="about__block-text">
                    <p>¡Hola! Mi nombre es Gonzalo Serra pero puedes llamarme <strong>Tonchi</strong>. Tengo 22 años y soy un apacionado por el mundo IT.</p>
                </div>
            </div>

            <div class="about__block">
                <div class="about__block-title">
                    <CareerIcon />
                    <h3>My career</h3>
                </div>
                <div class="about__block-text">
                    <p>En 2019 comencé a estudiar <strong>Ingeniería en Sistemas de Información</strong> en la Universidad Tecnológica Nacional FRRo y de forma autodidacta me centro en aprender y mejorar mis habilidades como <strong>Frontend Developer</strong>.</p>
                </div>
            </div>

            <div class="about__block">
                <div class="about__block-title">
                    <LearningIcon />
                    <h3>Learning</h3>
                </div>
                <div class="about__block-text">
                    <p>Actualmente, de forma autodidacta, estoy aprendiendo sobre vue.js y TypeScript. En cuanto a la universidad, estoy aprendiendo sobre Angular.js y Node.js.</p>
                </div>
            </div>
        </div>
    </section>
</template>

<style lang="scss">
    .about {
        width: 100%;
        min-height: 100vh;
        background: #fff;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 50px;

        &__list {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
            gap: 20px;
        }

        &__block {
            border: 1px solid var(--gray-color-200);
            border-radius: 10px;
            padding: 40px 20px 20px;
            position: relative;

            &-title {
                position: absolute;
                top: -30px;
                left: 20px;
                display: flex;
                align-items: center;
                gap: 20px;
                background-color: #fff;
                padding: 0 20px;

                svg {
                    width: 60px;
                }

                h3 {
                    font-size: 1.3rem;
                }
            }

            &-text {
                p {
                    line-height: 1.2;
                }
            }
        }
    }
</style>