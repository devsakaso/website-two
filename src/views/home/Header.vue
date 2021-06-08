<template>
  <header class="header l-header" id="header">
    <!-- トップロゴ -->
    <div class="header__logo">
      <img class="header__logo-image" src="@/assets/img/logo.svg" alt="Nexter logo">
      <span class="header__logo-text">LOGO</span>
    </div>

    <!-- タイトル -->
    <h3 class="heading-3">Best Select Wine</h3>
    <h1 class="heading-1">生産者の思いを、グラスへ</h1>

    <!-- ボタン -->
    <button class="btn header__btn">ベストセラーのワインを見る</button>

    <!-- メディア実績 -->
    <div class="header__seenon-text">メディア実績</div>
    <div class="header__seenon-logos">
      <img v-for="logo in seenOnLogos" :key="logo.src" :src="require(`@/assets/img/${logo.src}`)" :alt="logo.alt">
    </div>
  </header>
</template>

<script>
export default {
    setup() {
        const seenOnLogos = [
          {
            src: 'logo-bbc.png',
            alt: 'Seen on logo 1'
          },
          {
            src: 'logo-forbes.png',
            alt: 'Seen on logo 2'
          },
          {
            src: 'logo-techcrunch.png',
            alt: 'Seen on logo 3'
          },
          {
            src: 'logo-bi.png',
            alt: 'Seen on logo 4'
          },
        ]
        return {
          seenOnLogos,
        }
    },
}
</script>

<style lang="scss" scoped>
.header {
    display: grid;
    grid-template-rows: 1fr min-content minmax(6rem, min-content) 1fr;
    grid-template-columns: minmax(min-content, max-content);
    grid-row-gap: 1.5rem;
    justify-content: center;

    &__logo {
        justify-self: center;

      &-image,
      &-text {
        height: 3rem;
      }
      &-image {
        vertical-align: text-bottom;
      }
      &-text {
        font-size: 3rem;
        margin-left: 1rem;
        color: $color-primary;
        display: inline-block;
      }

    }

    &__btn {
      font-size: 1.8rem;
        align-self: start;
        justify-self: start;
    }

    &__seenon-text {
        display: grid;
        grid-template-columns: 1fr max-content 1fr;
        grid-column-gap: 1.5rem;
        align-items: center;

        font-size: 1.6rem;
        color: $color-grey-light-2;

        // 前後の線
        &::before,
        &::after {
            content: "";
            height: 1px;
            display: block;
            background-color: currentColor;
        }
    }

    &__seenon-logos {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        grid-column-gap: 3rem;
        justify-items: center;
        align-items: center;

        img {
            max-height: 2.5rem;
            max-width: 100%;
            filter: brightness(70%);
        }
    }
}
</style>