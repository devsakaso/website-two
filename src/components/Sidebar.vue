<template>
  <div class="l-sidebar">
    <nav class="menu__wrapper" :class="{'menu-open' : show}">
    <!-- メニューアイコン -->
    <button class="menu__icon" @click="showToggle">
        <span></span>
        <span></span>
        <span></span>
    </button>
    <!-- ナブリスト -->
    <ul class="menu__list">
      <li class="menu__item mb-sm" v-for="item in menuItems" :key="item" @click="showToggle">
        <a :href="item.link">{{ item.text }}</a>
      </li>
    </ul>
    </nav>
  </div>
</template>

<script>
import { ref } from 'vue'
export default {
  setup() {
    const show = ref(false)
    const showToggle = () => {
      show.value = !show.value
    }

    const menuItems = [
      {
        link: '#header',
        text: 'トップ'
      },
      {
        link: '#features',
        text: 'ショップの特徴について'
      },
      {
        link: '#story',
        text: 'お客様の声'
      },
      {
        link: '#wines',
        text: '人気のワインセット'
      },
      {
        link: '#gallery',
        text: 'ギャラリー'
      },
    ]
    return {
      show,
      showToggle,
      menuItems,
    }
  },
}
</script>

<style lang="scss" scoped>

.menu {
  &__wrapper {
    position: fixed;
    top: 0;
    left: 0;
    z-index: 10000;

    background: linear-gradient(rgba($color-primary, .8), rgba($color-primary, .8));
    width: 30rem; //navのwidth
    height: 100vh; //navのheight

    transform: translateX(-24rem);
    transition: all 0.5s;

    @media only screen and (max-width: $bp-large) {
      transform: translateX(0); //sidebar 6remなので
      height: 6vh;
      width: 100%;
    }
  }

  &__icon {
    position: fixed;
    top: 4rem;
    left: 25rem;
    transition: left 0.5s;

    border: none;
    width: 4rem;
    height: 4rem;
    background: transparent;
    cursor: pointer;
    outline: none;

    &:hover {
      & span {
        background: $color-tertiary;
      }
    }

    @media only screen and (max-width: $bp-large) {
      left: calc(100% - 6rem);
      top: 1rem;
    }
      
    & span {
      display: block;
      width: 4rem;
      height: 0.4rem;
      background: $color-secondary;
      margin-bottom: 1rem;
      transition: transform 0.5s ease-in-out, background .2s;

      &:last-child {
        margin-bottom: 0;
      }
    }
  }

  &__list {
    list-style: none;
    position: fixed;
    top: 15rem;
    left:3rem;
    font-size: 2rem;
    font-weight: bold;
    opacity: 0;
    visibility: hidden;
    transition: opacity 0.5s ease-in 0.2s;

  }
  &__item {

    & a {
        text-decoration: none;
        color: $color-secondary;
        transition: color 0.3s;

        &:hover {
          color: $color-tertiary;
        }
      }
    @media only screen and (max-width: $bp-large) {
      
    }

  }
}
.menu-open {

  &.menu {
    &__wrapper {
      transform: translateX(0) translateY(0);

      @media only screen and (max-width: $bp-large) {
          height: 100vh;
      }

      & .menu__icon {
        left: 12.5rem;

        @media only screen and (max-width: $bp-large) {
          left: calc(100% - 6rem);
          top: 1rem;
        }

        & span,
        &:hover span, {
          &:nth-child(1) {
            transition-delay: 70ms;
            transform: translateY(1.5rem) rotate(135deg);
          }
          &:nth-child(2) {
            transform: scale(0);
          }
          &:nth-child(3) {
            transition-delay: 140ms;
            transform: translateY(-1.5rem) rotate(-135deg);
          }
        }

      }
      & .menu__list {
        opacity: 1;
        visibility: visible;

        @media only screen and (max-width: $bp-large) {
          font-size: 2.5rem;
          top: 16rem;
          width: calc(100% - 6rem);
          display: flex;
          flex-direction: column;
          align-items: center;
          justify-content: center;
          row-gap: 3rem;
        }
      }
    }
  }

}
</style>