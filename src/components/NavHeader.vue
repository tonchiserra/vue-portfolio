<script setup>
    import GithubIcon from './icons/GithubIcon.vue'
    import InstagramIcon from './icons/InstagramIcon.vue'
    import LinkedInIcon from './icons/LinkedInIcon.vue'
    import TwitterIcon from './icons/TwitterIcon.vue'
</script>

<template>
    <div class="nav-header">
        <nav class="nav-header__content page-width">
            <a href="/" class="logo">GS</a>
            <ul>
                <li><a href="#Experience" class="underline">Experience</a></li>
                <li><a href="#About" class="underline">About</a></li>
            </ul>
            <ul>
                <li><a href="github.com/tonchiserra" target="_blank"><GithubIcon /></a></li>
                <li><a href="https://www.linkedin.com/in/serragonzalo/" target="_blank"><LinkedInIcon /></a></li>
                <li><a href="instagram.com/tonchiserra" target="_blank"><InstagramIcon /></a></li>
                <li><a href="twitter.com/tonchiserra" target="_blank"><TwitterIcon /></a></li>
            </ul>
        </nav>
    </div>
</template>

<style lang="scss">
    .nav-header {
        position: sticky;
        top: 0;
        left: 0;
        width: 100%;
        height: 64px;
        border-bottom: 1px solid var(--gray-color-200);
        background-color: #fff;
        z-index: 1;

        .nav-header__content {
            display: flex;
            align-items: center;
            justify-content: space-between;
            width: 100%;
            height: 100%;

            .logo {
                color: var(--second-color);
                font-weight: bold;
                font-size: 2.5rem;
            }

            ul {
                display: flex;
                align-items: center;
                justify-content: center;
                gap: 20px;

                li {
                    list-style: none;
                }
            }
        }
    }
</style>