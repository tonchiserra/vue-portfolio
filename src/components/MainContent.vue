<script setup>
    import ProjectsList from './ProjectsList.vue';
    import NavHeader from './NavHeader.vue';
</script>

<template>
    <main>
        <NavHeader />
        <ProjectsList />
    </main>
</template>

<style lang="scss" scoped>
    main {
        margin-top: 100vh;
        background: #fff;
        position: relative;
    }
</style>