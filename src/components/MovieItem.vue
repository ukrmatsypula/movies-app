<template>
  <div>Movie {{ movie.Title }}</div>
</template>

<script>
export default {
  name: 'MovieItem',
  props: {
    movie: {
      default: Object,
      required: true,
    },
  },
}
</script>

<style lang="scss" scoped>

</style>