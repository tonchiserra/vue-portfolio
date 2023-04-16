<script setup>
    defineProps(['project'])
</script>

<template>
    <div class="project">
        <div class="project__images">
            <img v-for="url in project.images" :key="url.split('/').pop()" :src="url" :alt="url.split('/').pop()">
        </div>
        <div class="project__info">
            <h3 class="title">{{ project.title }}</h3>
            <p class="description">{{ project.description }}</p>
        </div>
        <div class="project__technologies">
            <p v-for="(tech, index) in project.technologies" :key="index">{{ tech }}</p>
        </div>

        <div class="project__buttons">
            <a href="#" class="primary" v-if="project.demo === ''" disabled><span>Test</span></a>
            <a :href="project.demo" class="primary" v-else><span>Test</span></a>
            <a href="#" class="secondary" v-if="project.repo === ''" disabled><span>View code</span></a>
            <a :href="project.repo" class="secondary" v-else><span>View code</span></a>
        </div>
    </div>
</template>

<style lang="scss">
    .project {
        border-radius: 10px;
        animation: showProject 500ms ease;
        position: relative;
        overflow: hidden;
        transition: all 300ms ease;
        border: 1px solid rgba(0,0,0,.2);
        
        &:hover {
            box-shadow: 0 0 3rem rgba(0,0,0,.2);
            transform: translateY(-10px);
            border: 1px solid rgba(0,0,0,0);
        }

        &__info {
            padding: 20px;
            display: flex;
            flex-direction: column;
            gap: 20px;
        }
    
        &__technologies {
            display: flex;
            align-items: center;
            justify-content: flex-end;
            gap: 5px;
            padding: 0 20px 10px;
        }

        &__buttons {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 20px;
            width: 100%;
            height: 60px;
            transition: all 300ms ease;
        }
    }
</style>