<template>
  <div class="loader-wrap" v-if="isShowLoader">
    <BSpinner type="grow" variant="light" label="Loading..."></BSpinner>
  </div>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  name: "loader",
  computed: {
    ...mapGetters(["isShowLoader"]),
  },
};
</script>

<style lang="scss" scoped>
.loader-wrap {
  display: flex;
  justify-content: center;
  align-items: center;
  position: fixed;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  z-index: 100;
  background-color: rgba(0, 0, 0, 0.7);
}
</style>
