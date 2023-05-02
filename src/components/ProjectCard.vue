<script setup>
    defineProps(['project'])
    import { Splide, SplideSlide } from '@splidejs/vue-splide';

    let splideImgs = {
        type: 'loop',
        width: '100%',
        pagination: false,
        drag: false
    }
</script>

<template>
    <SplideSlide class="project">
        <Splide :options="splideImgs" class="project__images" aria-label="ProjectImage">
            <SplideSlide v-for="url in project.images" :key="url.split('/').pop()">
                <img :src="url" :alt="url.split('/').pop()">
            </SplideSlide>
        </Splide>
        <div class="project__info">
            <h3 class="title"><a target="_blank" :href="project.demo">{{ project.title }}</a></h3>
            <p class="description">{{ project.description }}</p>
        </div>
        <div class="project__technologies">
            <img v-for="(tech, index) in project.technologies" :key="tech + index" :src="'technologies/' + tech + '.svg'" :alt="tech" width="24" />
        </div>

        <!-- <div class="project__buttons"> -->
            <!-- <a href="#" class="primary" v-if="project.demo === ''" disabled><span>Test</span></a> -->
            <!-- <a :href="project.demo" class="primary" v-else><span>Test</span></a> -->
            <!-- <a href="#" class="secondary" v-if="project.repo === ''" disabled><span>View code</span></a> -->
            <!-- <a :href="project.repo" class="secondary" v-else><span>View code</span></a> -->
        <!-- </div> -->
    </SplideSlide>
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
        }

        &__info {
            padding: 20px;
            display: flex;
            flex-direction: column;
            gap: 20px;

            .title {
                font-size: 1.4rem;
            }
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

        &__images {
            display: flex;
            flex-direction: row;
            justify-content: flex-start;
            align-items: center;
            overflow: hidden;

            img {
                width: 100%;
            }
        }

        .splide {
            .splide__arrow {
                background: transparent;
            }
        }
    }
</style>