<template>
  <div>
    <h1>{{ category }}</h1>
    <hr />
    <ul v-for="article in articles" :key="article.id">
      <li>
        <nuxt-link
          :to="{
            name: 'id-article',
            params: { id: article.id, article: article.title },
          }"
          >{{ article.description }}</nuxt-link
        >
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      articles: [
        { id: 123, title: 'hoge', description: 'hoge' },
        { id: 234, title: 'fuga', description: 'fuga' },
        { id: 345, title: 'fizz', description: 'fizz' },
        { id: 456, title: 'buzz', description: 'buzz' },
      ],
    }
  },
  computed: {
    category() {
      return this.$route.params.category
    },
  },
}
</script>

<style lang="scss" scoped></style>
