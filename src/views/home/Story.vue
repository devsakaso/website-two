<template>
  <div class="story__pictures l-story__pictures">
    <img src="@/assets/img/story-1.jpg" alt="Couple with new house" class="story__img--1">
    <img src="@/assets/img/story-2.jpg" alt="New house" class="story__img--2">
  </div>

  <div class="story__content l-story__content" id="story">
    <h3 class="heading-3 mb-sm">Happy Customers</h3>
    <h2 class="heading-2 heading-2--dark mb-md">&ldquo;感動のワインと出会えました&rdquo;</h2>
    <p class="story__text">
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Tenetur distinctio necessitatibus pariatur voluptatibus. Quidem consequatur harum volupta!
    </p>
    <button class="btn">オンラインショップへはこちら</button>
  </div>
</template>


<style lang="scss" scoped>
.story {
    &__pictures {

        display: grid;
        grid-template-rows: repeat(6, 1fr);
        grid-template-columns: repeat(6, 1fr);
        align-items: center;

        @media only screen and (max-width: $bp-medium) {
            grid-column: 1 / -1;
            padding: 6rem;
        }
    }

    &__img--1 {
        width: 100%;
        grid-row: 2 / 6;
        grid-column: 2 / 6;
        box-shadow: 0 2rem 5rem rgba(#000, .1);

        @media only screen and (max-width: $bp-medium) {
            grid-column: 1 / 5;
            grid-row: 1 / -1;
        }
    }

    &__img--2 {
        width: 115%;
        grid-row: 4 / 6;
        grid-column: 4 / 7;
        z-index: 20;
        box-shadow: 0 2rem 5rem rgba(#000, .2);

        @media only screen and (max-width: $bp-medium) {
            grid-row: 1 / -1;
            width: 100%;
        }
    }

    &__content {
        /*
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: flex-start;
        */

        display: grid;
        align-content: center;
        justify-items: start;

        @media only screen and (max-width: $bp-medium) {
            grid-column: 1 / -1;
            grid-row: 5 / 6;
        }
    }

    &__text {
        font-size: 1.5rem;
        font-style: italic;
        margin-bottom: 4rem;
    }
}
</style>