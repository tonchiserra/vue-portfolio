<script setup>
    import ProjectCard from './ProjectCard.vue';
    import { Splide } from '@splidejs/vue-splide';

    const projects = [
        {
            title: "Valery Accesorios",
            description: "Layout and development of Shopify e-commerce components based on a mockup that the design team provided me. <br/>The highlight component developed by me is the infinite promo bar that appears in the header and others places of the store.",
            technologies: ["shopify", "javascript", "vue", "sass", "css", "html"],
            repo: "",
            demo: "https://valeryaccesorios.com.ar/",
            images: ["/valery/valery-1.png", "/valery/valery-2.png", "/valery/valery-3.png", "/valery/valery-4.png"]
        },
        {
            title: "Titulo",
            description: "descripcion",
            technologies: ["tecnologias"],
            repo: "sisisi",
            demo: "https://valeryaccesorios.com.ar/",
            images: []
        },
        {
            title: "Titulo",
            description: "descripcion",
            technologies: ["tecnologias"],
            repo: "sisisi",
            demo: "https://valeryaccesorios.com.ar/",
            images: []
        },
        {
            title: "Titulo",
            description: "descripcion",
            technologies: ["tecnologias"],
            repo: "sisisi",
            demo: "https://valeryaccesorios.com.ar/",
            images: []
        }
    ]

    let splideProjectsOptions = {
        type: 'loop',
        width: '100vw',
        perPage: 4,
        perMove: 1,
        focus: 'center',
        gap: '20px',
        updateOnMove: true,
        pagination: false,
        autoplay: true,
        interval: 2500,
        pauseOnHover: true,
        drag: false
    }
</script>

<template>
    <section class="projects">
        <h2 class="section-title">Projects & contributions</h2>

        <Splide :options="splideProjectsOptions" class="projects__list" aria-label="Projects & contributions">
            <ProjectCard v-for="(project, index) in projects" :key="index" :project="project" />
        </Splide>

        <p class="text-center">You can see all my projects and contributions in my <a href="https://github.com/tonchiserra">GitHub</a>.</p>
    </section>
</template>

<style lang="scss">
    .projects {
        width: 100%;
        min-height: 100vh;
        padding-top: 50px;
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
                box-shadow: 0 0 3rem rgba(0,0,0,.2);
                transform: translateY(-10px);
            }
        }
    }
</style>