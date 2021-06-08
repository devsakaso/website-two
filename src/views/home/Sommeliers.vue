<template>
  <div class="sommeliers l-sommeliers" id="sommeliers">
    <h3 class="heading-3 sommeliers__title">Top 3 ソムリエ</h3>
    <div class="sommeliers__list" v-for="item in items" :key="item">
      <img :src="require(`@/assets/img/${item.src}`)" :alt="item.alt" class="sommeliers__img">
      <div class="sommeliers__details">
          <h4 class="heading-4 heading-4--light">{{ item.name }}</h4>
          <p class="sommeliers__location">{{ item.location }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  setup() {
    const items = [
      {
        src: 'sommelier-1.jpeg',
        alt: 'Sommelier 1',
        name: '大阪 太郎',
        location: '大阪店'
      },
      {
        src: 'sommelier-2.jpeg',
        alt: 'Sommelier 3',
        name: '品川 花子',
        location: '品川支店'
      },
      {
        src: 'sommelier-3.jpeg',
        alt: 'Sommelier 3',
        name: '芦屋 一郎',
        location: '芦屋支店'
      },
    ]
    return {
      items,
    }
  },
}
</script>

<style lang="scss" scoped>
.sommeliers {
    display: grid;
    align-content: center;
    justify-content: center;
    justify-items: center;
    grid-row-gap: 2rem;

    @media only screen and (max-width: $bp-medium) {
      grid-template-columns: repeat(3, min-content max-content);
    }
    @media only screen and (max-width: $bp-small) {
      grid-template-columns: max-content;
    }

    &__title {
      @media only screen and (max-width: $bp-medium) {
        grid-column: 1 / -1;
      }
    }
    
    &__list {
        display: grid;
        grid-template-columns: min-content max-content;
        grid-column-gap: 2rem;
        grid-row-gap: 5vh;
        align-items: center;
        justify-self: start; //テキストが多い場合ずれるので


        @media only screen and (max-width: $bp-medium) {
            grid-template-columns: repeat(3, min-content max-content);
            grid-column-gap: 1rem;
        }

        // @media only screen and (max-width: $bp-small) {
        //     grid-template-columns: min-content max-content;
        // }
    }

    &__img {
        width: 7rem;
        border-radius: 50%;
        display: block;
    }

    &__location {
        text-transform: uppercase;
        color: $color-grey-light-2;
        margin-top: -3px;
    }
}
</style>