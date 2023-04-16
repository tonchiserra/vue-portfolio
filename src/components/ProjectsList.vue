<script setup>
    import ProjectCard from './ProjectCard.vue';

    const projects = [
        {
            title: "Valery Accesorios",
            description: "Layout and development of Shopify e-commerce components based on a mockup that the design team provided me. <br/>The highlight component developed by me is the infinite promo bar that appears in the header and others places of the store.",
            technologies: ["Shopify", "JavaScript", "Vue", "Sass", "CSS", "HTML"],
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
</script>

<template>
    <section class="projects">
        <h2 class="section-title">Projects & contributions</h2>

        <ul class="projects__list page-width">
            <ProjectCard v-for="(project, index) in projects" :key="index" :project="project" />
        </ul>

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

        &__list {
            display: grid;
            grid-template-columns: 1fr 1fr 1fr 1fr;
            gap: 20px;
        }
    }
</style>