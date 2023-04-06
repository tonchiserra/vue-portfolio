<template>
    <div class="project">
        <div class="project__info">
            <h3 class="title">Project title</h3>
            <p class="description">Lorem ipsum dolor sit amet consectetur adipisicing elit. Illum facilis beatae similique voluptas quibusdam dicta, soluta, autem, nisi debitis nulla eligendi nostrum? In, quaerat eveniet! Placeat quasi cum facere voluptatum. Lorem ipsum dolor, sit amet consectetur adipisicing elit. Ex optio repellendus eius perspiciatis debitis ipsa nam quos quibusdam animi recusandae laudantium neque delectus enim expedita quas ad, dicta aliquid ipsum.</p>
        </div>
        <div class="project__technologies">
            HTML, CSS, JS, Vue, Sass
        </div>

        <div class="project__buttons">
            <button class="primary"><span>Test</span></button>
            <button class="secondary"><span>View code</span></button>
        </div>
    </div>
</template>

<style>
    .project {
        background-color: #fff;
        border-radius: 10px;
        animation: showProject 500ms ease;
        position: relative;
        overflow: hidden;
    }

    .project__info {
        padding: 20px;
        display: flex;
        flex-direction: column;
        gap: 20px;
    }

    .project__technologies {
        display: flex;
        align-items: center;
        justify-content: flex-end;
        gap: 5px;
        padding: 0 20px 10px;
    }

    .project__buttons {
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 20px;
        width: 100%;
        position: absolute;
        bottom: -60px;
        left: 0;
        height: 60px;
        transition: all 300ms ease;
    }

    .project:hover .project__buttons {
        bottom: 0;
    }

    .project__buttons > button {
        height: 40px;
        width: 120px;
        border: none;
        border-radius: 5px;
        font-weight: bold;
        position: relative;
        overflow: hidden;
        transition: all 300ms ease;
        transition-delay: 100ms;
    }

    .project__buttons > button.primary {
        background: var(--second-color);
        border: 2px solid var(--second-color);
        color: #fff;
    }

    .project__buttons > button.secondary {
        background: #fff;
        border: 2px solid var(--second-color);
        color: var(--second-color);
    }

    .project__buttons > button::after {
        content: '';
        position: absolute;
        bottom: -200%;
        left: 0;
        width: 100%;
        height: 200%;
        border-top-left-radius: 100%;
        border-top-right-radius: 100%;
        background-color: var(--third-color);
        transition: all 300ms ease;
    }

    .project__buttons > button:hover {
        border: 2px solid var(--third-color);
        color: #fff;
    }

    .project__buttons > button:hover::after {
        bottom: 0;
    }

    @keyframes showProject {
        from {
            opacity: 0;
        }
        to {
            opacity: 1;
        }
    }
</style>