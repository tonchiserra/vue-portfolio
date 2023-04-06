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
        margin-top: 100vh;
        padding: 20px 0;
    }
</style>