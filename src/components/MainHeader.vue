<script setup>
  import ScrollIcon from './icons/ScrollIcon.vue';
</script>

<template>
  <header>
    <div class="main-title">
      <h2>Front-end Developer</h2>
      <h1>Gonzalo Serra</h1>
    </div>

    <button class="contact-button" @click="showContactPage()">
      <span>Contact me</span>
    </button>

    <ScrollIcon />
  </header>
</template>

<script>
  document.addEventListener("DOMContentLoaded", () => {
    setTimeout(() => {
      let contactButton = document.querySelector('.contact-button')
      if(!contactButton) return

      contactButton.style.animation = 'alertContactButton 5000ms ease infinite'
    }, 2000)
  })

  export default {
    methods: {
      showContactPage() {
        let contactPage = document.querySelector('.contact-form')
        if(!contactPage) return

        contactPage.classList.remove('d-none')
      }
    }
  }
</script>

<style lang="scss">
  header {
    height: 100vh;
    width: 100vw;
    position: fixed;
    top: 0;
    left: 0;
    display: flex;
    flex-direction: column;
    align-items: center;

    .main-title {
      width: max-content;
      margin: 0 auto;
      padding-top: 250px;

      h1 {
        background: -webkit-linear-gradient(left, var(--second-color),  var(--main-color));
        background: linear-gradient(to right, var(--second-color), var(--main-color));
        -webkit-background-clip: text;  
        -webkit-text-fill-color: transparent;
        font-size: 10rem;
        font-weight: 900;
        animation: showTitle 1300ms ease;
      }

      h2 {
        font-size: 2rem;
        padding-left: 3px;
        animation: showSubtitle 1300ms ease;
        font-family: var(--font-heading-family);
        text-transform: uppercase;
      }
    }

    .contact-button {
      background: transparent;
      border: none;
      outline: 2px solid #222;
      color: #222;
      width: 200px;
      margin-top: 80px;
      transition: all 300ms ease;
      transition-delay: 150ms;
      animation: showContactButton 1700ms ease;
      overflow: hidden;

      &::after,
      &::before {
        content: '';
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 200%;
        z-index: -1;
        transform: translateY(50%);
        border-top-right-radius: 100%;
        border-top-left-radius: 100%;
      }

      &::after {
        background-color: var(--second-color);
        transition: all 300ms ease;
      }

      &::before {
        background-color: var(--main-color);
        transition: all 300ms ease;
      }
    }

    .contact-button:hover {
      outline: 2px solid var(--main-color);
      color: #fff;

      &::after {
        transform: translateY(-100%);
      }
      &::before {
        transform: translateY(-50%);
      }
    }
  }

  @keyframes showTitle {
    0% {
      transform: translateY(150px);
      opacity: 0;
    }
    50% {
      transform: translateY(150px);
      opacity: 0;
    }
    100% {
      transform: translateY(0);
      opacity: 1;
    }
  }

  @keyframes showSubtitle {
    0% {
      transform: translateX(-150px);
      opacity: 0;
    }
    50% {
      transform: translateX(-150px);
      opacity: 0;
    }
    100% {
      transform: translateX(0);
      opacity: 1;
    }
  }

  @keyframes showContactButton {
    0% {
      transform: scaleX(0%);
      opacity: 0;
    }
    70% {
      transform: scaleX(0%);
      opacity: 1;
    }
    80% {
      transform: scaleX(140%);
      opacity: 1;
    }
    90% {
      transform: scaleX(70%);
      opacity: 1;
    }
    95% {
      transform: scaleX(120%);
      opacity: 1;
    }
    100% {
      transform: scaleX(100%);
      opacity: 1;
    }
  }

  @keyframes alertContactButton {
    0% {
      outline-offset: 0;
    }
    60% {
      outline-offset: 0;
    }
    70% {
      outline-offset: 10px;
    }
    80% {
      outline-offset: 0;
    }
    90% {
      outline-offset: 10px;
    }
    100% {
      outline-offset: 0;
    }
  }
</style>