<script setup>
    import ProjectCard from './ProjectCard.vue';
    import { Splide } from '@splidejs/vue-splide';

    const projects = [
        {
            title: "Valery Accesorios",
            subtitle: "Contribution",
            description: "Layout and development of Shopify e-commerce components based on a mockup that the design team provided me. The highlight component developed by me is the infinite promo bar that appears in the header and others places of the store.",
            technologies: ["shopify", "javascript", "vue", "sass", "css", "html"],
            repo: "",
            demo: "https://valeryaccesorios.com.ar/",
            image: "/projects_img/valery.png"
        },
        {
            title: "Mac Center",
            subtitle: "Contribution",
            description: "I developed differents features and fix some issues in the Mac Center store. This is a Premium Partner Reseller of Apple, is a big store with multiples shops at Colombia, Perú, Panamá and República Dominicana.",
            technologies: ["shopify", "javascript", "vue", "sass", "css", "html"],
            repo: "",
            demo: "https://mac-center.com/",
            image: "/projects_img/mac-center.png"
        }
    ]

    let splideProjectsOptions = {
        type: 'loop',
        width: '100vw',
        perPage: 1.5,
        perMove: 1,
        focus: 'center',
        gap: '100px',
        updateOnMove: true,
        pagination: false,
        autoplay: true,
        interval: 4000,
        pauseOnHover: true,
        drag: false
    }
</script>

<template>
    <section id="Experience" class="projects">
        <div class="section-title page-width">
            <div class="title">
                <div class="title__point"></div>
                <h2 class="title__text">Projects & contributions</h2>
            </div>
            <a class="underline" href="https://github.com/tonchiserra">View all</a>
        </div>

        <Splide :options="splideProjectsOptions" class="projects__list" aria-label="Projects & contributions">
            <ProjectCard v-for="(project, index) in projects" :key="index" :project="project" />
        </Splide>
    </section>
</template>

<style lang="scss">
    .projects {
        width: 100%;
        max-width: 1920px;
        min-height: 100vh;
        background: #fff;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 50px;

        .splide {
            .splide__track {
                overflow: unset;
            }

            .project.is-active {
                opacity: 1;
            }

            .splide__arrow {
                background: transparent;
            }
        }
    }
</style>