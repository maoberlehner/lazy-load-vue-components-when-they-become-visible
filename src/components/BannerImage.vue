<template>
  <div class="BannerImage">
    <slot/>
  </div>
</template>

<script>
export default {
  name: `BannerImage`,
};
</script>

<style lang="scss">
.BannerImage {
  max-width: 80em;
  margin-right: auto;
  margin-left: auto;

  img {
    width: 100%;
  }
}
</style>
