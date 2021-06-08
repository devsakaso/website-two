<template>
  <section class="features l-features" id="features">
    <div class="feature" v-for="item in featuresItems" :key="item">
      <div class="feature__icon">
        <Icon :name="item.icon"></Icon>
      </div>
      <h4 class="heading-4 heading-4--dark">{{ item.title }}</h4>
      <p class="feature__text">{{ item.text }}</p>
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
    const featuresItems = [
    {
      // icon: '<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z" />',
      icon: 'clock',
      title: '毎日スピード出荷',
      text: 'Voluptatum mollitia quae. Vero ipsum sapiente molestias accusamus rerum sed a eligendi aut quia.'
    },
    {
      // icon: '<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7h8m0 0v8m0-8l-8 8-4-4-6 6" />',
      icon: 'growing',
      title: '1000種類以上常時取り扱い',
      text: 'Voluptatum mollitia quae. Vero ipsum sapiente molestias accusamus rerum sed a eligendi aut quia.'
    },
    {
      // icon: '<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 8l3 5m0 0l3-5m-3 5v4m-3-5h6m-6 3h6m6-3a9 9 0 11-18 0 9 9 0 0118 0z" />',
      icon: 'price',
      title: '1万円以上で送料無料',
      text: 'Voluptatum mollitia quae. Vero ipsum sapiente molestias accusamus rerum sed a eligendi aut quia.'
    },
    {
      icon: 'expert',
      title: 'プロ・ソムリエが厳選',
      text: 'Voluptatum mollitia quae. Vero ipsum sapiente molestias accusamus rerum sed a eligendi aut quia.'
    },
    {
      icon: 'building',
      title: '自社で直輸入・直販',
      text: 'Voluptatum mollitia quae. Vero ipsum sapiente molestias accusamus rerum sed a eligendi aut quia.'
    },
    {
      icon: 'star',
      title: '希少なワイン',
      text: 'Voluptatum mollitia quae. Vero ipsum sapiente molestias accusamus rerum sed a eligendi aut quia.'
    },
  ]
  return {
    featuresItems,
    }
  },
}
</script>

<style lang="scss" scoped>

.feature {

    float: left;
    width: 33.3333%;
    margin-bottom: 6rem;

    @supports(display: grid) {
        width: auto;
        margin-bottom: 0;
    }

    display: grid;
    grid-template-columns: min-content 1fr;
    grid-row-gap: 1.5rem;
    grid-column-gap: 2.5rem;

    &__icon {
        grid-row: 1 / span 2;
    }

    &__text {
        font-size: 1.7rem;
    }
}
</style>