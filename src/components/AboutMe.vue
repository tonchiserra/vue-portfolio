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
                    <p>¡Hi! My name is Gonzalo Serra but you can call me <strong>Tonchi</strong>. I am 22 years old and I am passionate about IT world.</p>
                </div>
            </div>

            <div class="about__block">
                <div class="about__block-title">
                    <CareerIcon />
                    <h3>My career</h3>
                </div>
                <div class="about__block-text">
                    <p>In 2019 I started studying <strong>Information Systems Engineering</strong> at Universidad Tecnológica Nacional FRRo and in a self-taught way I focus on learning and improving my skills as <strong>Web Developer</strong>.</p>
                </div>
            </div>

            <div class="about__block">
                <div class="about__block-title">
                    <LearningIcon />
                    <h3>Learning</h3>
                </div>
                <div class="about__block-text">
                    <p>Current, in a self-taught way, i am learning about <strong>Vue.js</strong> and <strong>TypeScript</strong>. In the university, I am learning about <strong>Node.js</strong>.</p>
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
                height: 55px;

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