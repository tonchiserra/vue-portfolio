<script setup>
    import { SplideSlide } from '@splidejs/vue-splide';
    import GithubIcon from './icons/GithubIcon.vue';
    import ExternalLinkIcon from './icons/ExternalLinkIcon.vue';

    defineProps(['project'])
</script>

<template>
    <SplideSlide class="project">
        <a :href="project.demo || ''" target="_blank" class="project__image">
            <img :src="project.image" :alt="project.image.split('/').pop()">
        </a>
        <div class="project__info">
            <h5 class="subtitle">{{ project.subtitle }}</h5>
            <h3 class="title"><a target="_blank" :href="project.demo">{{ project.title }}</a></h3>
            <p class="description">{{ project.description }}</p>
            <div class="technologies">
                <img v-for="(tech, index) in project.technologies" :key="tech + index" :src="'technologies/' + tech + '.svg'" :alt="tech" width="24" />
            </div>
            <div class="links">
                <a href="#" class="primary" v-if="project.demo === ''" disabled><span><ExternalLinkIcon /></span></a>
                <a :href="project.demo" class="primary" target="_blank" v-else><span><ExternalLinkIcon /></span></a>
                <a href="#" class="secondary" v-if="project.repo === ''" disabled><span><GithubIcon /></span></a>
                <a :href="project.repo" class="secondary" target="_blank" v-else><span><GithubIcon /></span></a>
            </div>
        </div>
    </SplideSlide>
</template>

<style lang="scss">
    .project {
        animation: showProject 500ms ease;
        position: relative;
        overflow: hidden;
        transition: all 300ms ease;
        height: 400px;
        display: flex;
        flex-direction: column;
        align-items: flex-end;
        justify-content: space-between;
        opacity: .2;

        &__image {
            position: absolute;
            left: 0;
            top: 0;
            bottom: 0;
            margin: auto 0;
            z-index: 0;
            height: 100%;
            width: 70%;

            img {
                object-fit: cover;
                width: 100%;
                height: 100%;
                border-radius: 5px;
            }
        }

        &__info {
            padding: 40px 0;
            height: 100%;
            display: flex;
            flex-direction: column;
            align-items: flex-end;
            justify-content: center;

            .subtitle {
                font-weight: normal;
                font-size: 1rem;
                margin-bottom: 5px;
            }

            .title {
                font-size: 1.4rem;
                margin-bottom: 25px;

                a:hover {
                    color: var(--text-color);
                }
            }

            .description {
                background: #fff;
                border: 1px solid var(--gray-color-200);
                border-radius: 5px;
                padding: 25px 30px;
                text-align: right;
                max-width: 50%;
                margin-bottom: 25px;
                z-index: 1;
            }

            .technologies {
                display: flex;
                align-items: center;
                justify-content: flex-end;
                gap: 5px;
                margin-bottom: 25px;
            }

            .links {
                display: flex;
                align-items: center;
                gap: 20px;

                a svg path {
                    transition: all 300ms ease;
                }

                a:hover svg path {
                    fill: var(--second-color);
                }
            }
        }
    }
</style>