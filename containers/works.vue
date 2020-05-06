<template>
  <section id="works" class="works-wrapper">
    <pageTitle title="Works" />
    <div class="works">
      <work-box v-for="work in works" :key="work.link" :item="work" />
    </div>
  </section>
</template>

<script>
import pageTitle from '@/components/pageTitle'
import workBox from '@/components/workBox'

export default {
  name: 'Works',
  components: {
    pageTitle,
    workBox,
  },
  data() {
    return {
      works: [
        {
          name: 'Portfolio',
          content: '',
          subContent: 'Vue.js, Nuxt',
          link: 'https://github.com/KomiyaShinnosuke/portfolio2',
        },
        {
          name: 'movie review site...',
          content: '',
          subContent: '',
          link: '',
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
@import '@/assets/styles/_mixin.scss';

.works-wrapper {
  @include section;
}

.works {
  @include box-wrapper;
}

a {
  text-decoration: none;
}
</style>
