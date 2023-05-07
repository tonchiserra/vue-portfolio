<template>
    <div class="nav-header">
        <nav class="nav-header__content page-width">
            <ul>
                <li><a href="#Experience" class="underline">Experience</a></li>
                <li><a href="" class="underline">About</a></li>
            </ul>
            <ul>
                <li><a href="">GitHub</a></li>
                <li><a href="">LinkedIn</a></li>
                <li><a href="">Instagram</a></li>
                <li><a href="">Twitter</a></li>
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
        height: 48px;
        border-bottom: 1px solid var(--gray-color-200);

        .nav-header__content {
            display: flex;
            align-items: center;
            justify-content: space-between;
            width: 100%;
            height: 100%;

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