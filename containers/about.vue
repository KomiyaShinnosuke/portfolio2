<template>
  <section id="about" class="about-wrapper">
    <pageTitle title="About" />
    <div class="box-wrapper">
      <table>
        <tbody>
          <tr v-for="(contact, index) in contacts" :key="index">
            <th>{{ contact.key }}</th>
            <td v-if="contact.url" class="last-td">
              <a :href="contact.url" target="_blank" rel="noopener noreferrer">
                {{ contact.value }}
              </a>
            </td>
            <td v-else class="last-td">
              {{ contact.value }}
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </section>
</template>

<script>
import pageTitle from '@/components/pageTitle'

export default {
  name: 'About',
  components: {
    pageTitle,
  },

  data() {
    return {
      contacts: [
        { key: 'Name', value: '小宮 慎ノ介 (Shin Komi)', url: '' },
        { key: 'University', value: '東工大', url: '' },
        {
          key: 'GitHub',
          value: 'KomiyaShinnosuke',
          url: 'https://github.com/KomiyaShinnosuke',
        },
        {
          key: 'Qiita',
          value: 'KomiyaShinnosuke',
          url: 'https://qiita.com/KomiyaShinnosuke',
        },
        {
          key: 'Facebook',
          value: '小宮 慎ノ介',
          url: 'https://www.facebook.com/shinnosuke.komiya.9',
        },
        { key: 'Mail', value: 'shinnosuke828[at]gmail.com', url: '' },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
@import '@/assets/styles/_color.scss';
@import '@/assets/styles/_mixin.scss';

.about-wrapper {
  @include section;
}

.box-wrapper {
  @include box-wrapper;
  color: $text-color;

  table {
    text-align: left;
  }

  th {
    padding-right: 20px;
    font-weight: normal;
    color: $sub-text-color;
  }

  td {
    font-size: 20px;
    padding: 5px 8px 5px 0;
  }
}

a {
  text-decoration: none;
}

/*スマートフォン*/
@media (max-width: 670px) {
  .box-wrapper {
    td {
      display: block;
      font-size: 16px;
      width: 100%;
      padding: 5px 0;
      border-bottom: none;
    }
  }
}
</style>
