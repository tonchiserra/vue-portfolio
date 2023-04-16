<script setup>
    import ProjectsList from './ProjectsList.vue';
    import ContactForm from './ContactForm.vue';
</script>

<template>
    <main>
        <ProjectsList />
        <ContactForm />
    </main>
</template>

<style scoped>
    main {
        position: absolute;
        top: 100vh;
        left: 0;
        width: 100%;
        z-index: 2;
    }
</style>