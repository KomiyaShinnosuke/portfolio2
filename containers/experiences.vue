<template>
  <section id="experiences" class="experiences-wrapper">
    <pageTitle title="Experiences" />
    <v-app>
      <v-timeline :reverse="reverse" :dense="dense">
        <v-timeline-item
          v-for="(experience, index) in experiences"
          :key="index"
          color="#2F80ED"
          fill-dot
          small
        >
          <span slot="">{{ experience.term }}</span>
          <span class="elevation-2">
            <v-card-title class="headline">
              {{ experience.key + ' ' + experience.value }}
            </v-card-title>
            <v-card-text>
              {{ experience.description }}
            </v-card-text>
          </span>
        </v-timeline-item>
      </v-timeline>
    </v-app>
  </section>
</template>

<script>
import pageTitle from '@/components/pageTitle'

export default {
  name: 'Experiences',
  components: {
    pageTitle,
  },

  data() {
    return {
      width: window.innerWidth,
      experiences: [
        {
          key: 'Link and Motivation',
          value: 'フロントエンジニア',
          term: '2019/11 ~ Present',
          description:
            'モチベーションクラウドのフロントエンドの開発に携わっております。',
        },
        {
          key: 'どこか',
          value: 'エンジニア？',
          term: 'Future ~',
          description:
            '今のところ転職予定はないが、恐らく今後もエンジニアとしては働くのかなーと思います。',
        },
      ],
    }
  },

  computed: {
    dense() {
      return !(this.width > 670)
    },
    reverse() {
      return this.width > 670
    },
  },
  mounted() {
    window.addEventListener('resize', this.handleResize)
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.handleResize)
  },

  methods: {
    handleResize() {
      // resizeのたびにこいつが発火するので、ここでやりたいことをやる
      this.width = window.innerWidth
    },
  },
}
</script>

<style lang="scss" scoped>
@import '@/assets/styles/_color.scss';
@import '@/assets/styles/_mixin.scss';
@import '~vuetify/src/styles/styles.sass';

.experiences-wrapper {
  @include section;
  background-color: $background-color1;
}

.headline {
  justify-content: center;
}
</style>
