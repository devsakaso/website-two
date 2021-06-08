<template>

<!-- Features & Wine共通 -->
  <!-- priceアイコン -->
  <svg v-if="name === 'price'" xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 8l3 5m0 0l3-5m-3 5v4m-3-5h6m-6 3h6m6-3a9 9 0 11-18 0 9 9 0 0118 0z" />
  </svg>

<!-- Features -->
  <!-- 時計アイコン -->
  <svg v-if="name === 'clock'" xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 feature__icon" fill="none" viewBox="0 0 24 24" stroke="currentColor">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z" />
  </svg>

  <!-- 成長アイコン -->
  <svg v-if="name === 'growing'" xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 feature__icon" fill="none" viewBox="0 0 24 24" stroke="currentColor">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7h8m0 0v8m0-8l-8 8-4-4-6 6" />
  </svg>

  <!-- アカデミックアイコン -->
  <svg v-if="name === 'expert'" xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 feature__icon" fill="none" viewBox="0 0 24 24" stroke="currentColor">
   <path d="M12 14l9-5-9-5-9 5 9 5z" />
   <path d="M12 14l6.16-3.422a12.083 12.083 0 01.665 6.479A11.952 11.952 0 0012 20.055a11.952 11.952 0 00-6.824-2.998 12.078 12.078 0 01.665-6.479L12 14z" />
   <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 14l9-5-9-5-9 5 9 5zm0 0l6.16-3.422a12.083 12.083 0 01.665 6.479A11.952 11.952 0 0012 20.055a11.952 11.952 0 00-6.824-2.998 12.078 12.078 0 01.665-6.479L12 14zm-4 6v-7.5l4-2.222" />
  </svg>

  <!-- 建物アイコン -->
  <svg v-if="name === 'building'" xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 feature__icon" fill="none" viewBox="0 0 24 24" stroke="currentColor">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 14v3m4-3v3m4-3v3M3 21h18M3 10h18M3 7l9-4 9 4M4 10h16v11H4V10z" />
  </svg>

  <!-- スターアイコン -->
  <svg v-if="name === 'star'" xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 feature__icon" fill="none" viewBox="0 0 24 24" stroke="currentColor">
   <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 3v4M3 5h4M6 17v4m-2-2h4m5-16l2.286 6.857L21 12l-5.714 2.143L13 21l-2.286-6.857L5 12l5.714-2.143L13 3z" />
  </svg>


<!-- Wines -->
  <!-- likeアイコン -->
  <svg v-if="name === 'like'" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z" />
  </svg>
<!-- locationアイコン -->
  <svg v-if="name === 'location'" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z" />
    <path stroke-linecap="round" stroke-linejoin="round"  stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z" />
  </svg>
<!-- typesアイコン -->
  <svg v-if="name === 'types'" xmlns="http://www.w3.org/2000/svg"  fill="none" viewBox="0 0 24 24" stroke="currentColor">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19.428 15.428a2 2 0 00-1.022-.547l-2.387-.477a6 6 0 00-3.86.517l-.318.158a6 6 0 01-3.86.517L6.05 15.21a2 2 0 00-1.806.547M8 4h8l-1 1v5.172a2 2 0 00.586 1.414l5 5c1.26 1.26.367 3.414-1.415 3.414H4.828c-1.782 0-2.674-2.154-1.414-3.414l5-5A2 2 0 009 10.172V5L8 4z" />
  </svg>
<!-- varietiesアイコン -->
  <svg v-if="name === 'varieties'" xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 5a2 2 0 012-2h10a2 2 0 012 2v16l-7-3.5L5 21V5z" />
  </svg>

</template>

<script>
export default {
  props: ['name']
}
</script>

<style lang="scss" scoped>
.feature {
  &__icon {
    svg {
      fill: $color-primary;
      width: 4.5rem;
      height: 4.5rem;
      transform: translateY(-1rem);
    }
  }
}

.wine {
  &__location,
  &__types,
  &__varieties,
  &__price {
    svg {
      fill: $color-primary;
      height: 2rem;
      width: 2rem;
      margin-right: 1rem;
    }
  }
  &__like {
    svg {
      fill: $color-tertiary;
      height: 2.5rem;
      width: 2.5rem;
    }
  }
}
</style>