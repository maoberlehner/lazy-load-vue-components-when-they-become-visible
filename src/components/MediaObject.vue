<template>
  <div class="MediaObject">
    <div class="MediaObject__figure">
      <slot name="image"/>
    </div>
    <div class="MediaObject__body">
      <slot/>
    </div>
  </div>
</template>

<script>
export default {
  name: `MediaObject`,
};
</script>

<style lang="scss">
@import '../assets/scss/settings/**/*';

.MediaObject {
  display: flex;
  align-items: center;
}

.MediaObject__body {
  margin-left: setting-spacing(m);
}
</style>
