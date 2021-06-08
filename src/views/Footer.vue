<template>
  <footer class="l-footer" id="footer">
    <ul class="nav">
      <li v-for="item in footerData" :key="item" class="nav__item"><a :href="item.link" class="nav__link">{{ item.text }}</a></li>
    </ul>
    <p class="copyright">
      &copy; {{ copyDetails.year }} <a :href="copyDetails.link" class="copyright__link">{{ copyDetails.name }}</a>. All right reserved
    </p>
  </footer>
</template>

<script>
export default {
  setup() {
    const footerData = [
      {
        link: '#',
        text: 'お支払い方法について'
      },
      {
        link: '#',
        text: 'お問い合わせ'
      },
      {
        link: '#',
        text: 'ご利用ガイド'
      },
      {
        link: '#',
        text: 'メールマガジン登録/解除'
      },
      {
        link: '#',
        text: 'ショップ＆イベント情報'
      },
      {
        link: '#',
        text: 'プライバシー･ポリシー'
      },
    ]
    const copyDetails = {
        year: 2021,
        link: 'https://www.sakaso-portfolio.com/',
        name: 'Sakai'
      }
    return {
      footerData,
      copyDetails,
    }
  },
}
</script>
<style lang="scss" scoped>

.nav {
    list-style: none;

    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(15rem, 1fr));
    grid-gap: 2rem;
    align-items: center;

    &__link:link,
    &__link:visited {
        font-size: 1.4rem;
        color: #fff;
        text-decoration: none;
        font-family: $font-display;
        text-transform: uppercase;
        text-align: center;
        padding: 1.5rem;
        display: block;
        transition: all .2s;
    }

    &__link:hover,
    &__link:active {
        background-color: rgba(#fff, .05);
        transform: translateY(-3px);
    }
}

.copyright {
    font-size: 1.5rem;
    color: $color-grey-light-2;
    margin-top: 6rem;
    margin-right: auto;
    margin-left: auto;
    text-align: center;
    width: 70%;

    &__link {
      text-decoration: none;
      color: $color-primary;

      &:hover {
        color: $color-primary-dark;
      }
    }
}
</style>