<template>
  <section class="wines l-wines" id="wines">
    <!-- データ -->
    <div class="wine" v-for="item in winesData" :key="item">
        <img :src="require(`@/assets/img/${item.src}`)" :alt="item.alt" class="wine__img">
        <!-- likeアイコン -->
        <div class="wine__like">
          <Icon name="like"></Icon>
        </div>
        <!-- タイトル -->
        <h5 class="wine__name">{{ item.title }}</h5>

        <!-- ロケーション -->
        <div class="wine__location">
          <Icon name="location"></Icon>
          <p>{{ item.locationText }}</p>
        </div>

        <!-- タイプ（赤・白） -->
        <div class="wine__types">
          <Icon name="types"></Icon>
          <p>{{ item.typeText }}</p>
        </div>

        <!-- 品種 -->
        <div class="wine__varieties">
          <Icon name="varieties"></Icon>
          <p>{{ item.varietiesText }}</p>
        </div>

        <div class="wine__price">
          <Icon name="price"></Icon>
          <p>{{ item.priceText }}</p>
        </div>

        <button class="btn wine__btn">詳細をみる</button>
    </div>
  </section>
</template>

<script>
import Icon from '@/shared/Icon.vue'

export default {
  components: {
    Icon,
  },
  setup() {
    const winesData = [
      {
        src: 'wine-1.jpg',
        alt: 'wine 1',
        title: '大人気デイリーワインセット',
        locationText: 'イタリア他',
        typeText: '赤ワイン',
        varietiesText: 'メルロー他',
        priceText: '10,000円'
      },
      {
        src: 'wine-2.jpg',
        alt: 'wine 2',
        title: 'ボルドー名門シャトーセット',
        locationText: 'フランス',
        typeText: '赤ワイン',
        varietiesText: 'カベルネ・ソーヴィニヨン他',
        priceText: '50,000円'
      },
      {
        src: 'wine-3.jpg',
        alt: 'wine 3',
        title: 'ソムリエ厳選ワインセット',
        locationText: 'スペイン他',
        typeText: '赤・白ワイン',
        varietiesText: 'カルメネール他',
        priceText: '30,000円'
      },
      {
        src: 'wine-4.jpg',
        alt: 'wine 4',
        title: '神の雫記載ワインセット',
        locationText: 'チリ他',
        typeText: '赤・白ワイン',
        varietiesText: 'ソービニオンブラン他',
        priceText: '35,000円'
      },
      {
        src: 'wine-5.jpg',
        alt: 'wine 5',
        title: '葡萄品種を知るワインセット',
        locationText: 'アメリカ他',
        typeText: '赤ワイン',
        varietiesText: 'ピノ・ノワール他',
        priceText: '25,000円'
      },
      {
        src: 'wine-6.jpg',
        alt: 'wine 6',
        title: 'シャルドネ飲み比べセット',
        locationText: '南アフリカ他',
        typeText: '白ワイン',
        varietiesText: 'シャルドネ',
        priceText: '18,000円'
      },
    ]
    
    return {
      winesData,
    }
  },
}
</script>

<style lang="scss" scoped>
.wines {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(25rem, 1fr));
    grid-gap: 7rem;
}

.wine {
    background-color: $color-grey-light-1;

    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-row-gap: 3.5rem;

    &__img {
        width: 100%;
        grid-row: 1 / 2;
        grid-column: 1 / -1;
        z-index: 1;
        object-fit: contain;
    }

    &__like {
        grid-row: 1 / 2;
        grid-column: 2 / 3;
        z-index: 2;
        justify-self: end;
        margin: 1rem;
    }

    &__name {
        grid-row: 1 / 2;
        grid-column: 1 / -1;
        justify-self: center;
        align-self: end;
        z-index: 3;

        width: 80%;
        font-family: $font-display;
        font-size: 1.6rem;
        text-align: center;
        padding: 1.25rem;
        background-color: $color-secondary;
        color: #fff;
        font-weight: 400;
        transform: translateY(50%);
    }

    &__location,
    &__types {
        margin-top: 2.5rem;
    }

    &__location,
    &__types,
    &__varieties,
    &__price {

        font-size: 1.5rem;
        margin-left: 2rem;
        padding-right: 1rem;

        display: grid;
        grid-template-rows: 1fr;
        grid-template-columns: 2rem minmax(2rem, 1fr);
        grid-gap: 1rem;

    }

    &__btn {
        grid-column: 1 / -1;
    }
}

</style>