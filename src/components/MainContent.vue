<script setup>
    import ProjectsList from './ProjectsList.vue'
    import NavHeader from './NavHeader.vue'
    import AboutMe from './AboutMe.vue'
</script>

<template>
    <main>
        <NavHeader />
        <ProjectsList />
        <AboutMe />
    </main>
</template>

<style lang="scss" scoped>
    main {
        margin-top: 100vh;
        background: #fff;
        position: relative;
    }
</style>