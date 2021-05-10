<template>
  <div class="movies-pagination d-flex justify-content-center">
    <BPagination
      v-model="currentPage"
      :per-page="perPage"
      :total-rows="total"
      prev-text="Prev"
      next-text="Next"
    />

    {{ currentPage }}
  </div>
</template>

<script>
export default {
  name: "MoviesPagination",
  data: () => ({
    currentPage: 1,
    total: 100,
    perPage: 12,
  }),
};
</script>

<style lang="scss" scoped>
.movies-pagination {
  margin-top: 30px;
}

.movies-pagination /deep/ .pagination .page-item .page-link {
  background-color: transparent;
  z-index: 12;
  color: #fff;
  box-shadow: none;
}

.movies-pagination /deep/ .pagination .page-item.active .page-link {
  background-color: #fff;
  color: #000;
}

.movies-pagination /deep/ .pagination .page-item.disabled .page-link {
  color: rgba(231, 222, 222, 0.3);
}
</style>
