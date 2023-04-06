<script setup>
    import ProjectCard from './ProjectCard.vue';
</script>

<template>
    <section class="projects">
        <ul class="projects__list page-width">
            <ProjectCard />
            <ProjectCard />
            <ProjectCard />
            <ProjectCard />
            <ProjectCard />
            <ProjectCard />
            <ProjectCard />
            <ProjectCard />
            <ProjectCard />
        </ul>
    </section>
</template>

<style>
    .projects {
        width: 100%;
        padding-top: 50px;
        margin-top: 100px;
        background: linear-gradient(135deg, #fff, #73b6f9);
    }

    .projects__list {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
        gap: 20px;
    }
</style>