<template>
  <div>{{ article }}</div>
</template>

<script>
export default {
  computed: {
    article() {
      return this.$route.params.article
    },
  },
}
</script>

<style lang="scss" scoped></style>
