<template>
    <div class="scroll-icon">
        <div class="scroll-icon__border">
            <div class="scroll-icon__ball"></div>
        </div>
    </div>
</template>

<style lang="scss">
    .scroll-icon {
        position: absolute;
        bottom: 50px;
        left: 0;
        width: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
        animation: showScrollIcon 2300ms ease;

        &__border {
            width: 20px;
            height: 35px;
            border-radius: 10px;
            border: 3px solid #222;
            display: flex;
            align-items: flex-start;
            justify-content: center;
            overflow: hidden;
        }

        &__ball {
            width: 10px;
            height: 10px;
            border-radius: 100px;
            background-color: #222;
            animation: scrollBall 2s ease-in-out infinite;
        }
    }

    @keyframes showScrollIcon {
        0% {
            transform: translateY(100px);
        }
        80% {
            transform: translateY(100px);
        }
        100% {
            transform: translateY(0);
        }
    }

    @keyframes scrollBall {
        0% {
            transform: translateY(35px);
            opacity: 1;
        }
        25% {
            transform: translateY(2px);
            opacity: 1;
        }
        60% {
            transform: translateY(2px);
            opacity: 0;
        }
        100% {
            transform: translateY(2px);
            opacity: 0;
        }
    }
</style>