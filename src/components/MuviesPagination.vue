<template>
  <div class="movies-pagination d-flex justify-content-center">
    <BPagination
      v-model="currentPageModel"
      :per-page="perPage"
      :total-rows="total"
      prev-text="Prev"
      next-text="Next"
    />
  </div>
</template>

<script>
export default {
  name: "MoviesPagination",
  props: {
    currentPage: {
      typeof: Number,
      default: 1,
    },
    total: {
      type: Number,
      default: 1,
    },
    perPage: {
      type: Number,
      default: 1,
    },
  },
  computed: {
    currentPageModel: {
      get() {
        return this.currentPage;
      },
      set(value) {
        this.$emit("pageChanged", value);
      },
    },
  },
};
</script>

<style lang="scss" scoped>
.movies-pagination {
  margin-top: auto;
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
