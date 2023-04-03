<template>
  <div class="accommodations-bedrooms--item---img">
    <img :src="image" />
  </div>
</template>

<script>
export default {
  name: "ImageBanner",
  props: {
    image: {
      type: String,
    },
  },
};
</script>

<style lang="scss" scoped>
.accommodations-bedrooms--item---img {
  & img {
    min-width: 290px;
    width: 100%;
    height: 90%;
    border-radius: 60px;
    cursor: pointer;
  }
}
</style>