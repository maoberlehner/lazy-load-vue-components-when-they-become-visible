<template>
  <div class="IntroText">
    <slot name="headline"/>
    <p class="IntroText__body">
      <slot/>
    </p>
  </div>
</template>

<script>
export default {
  name: `IntroText`,
};
</script>

<style lang="scss">
@import '../assets/scss/settings/**/*';

.IntroText {
  text-align: center;

  &__body {
    margin-top: setting-spacing(m);
    font-size: 1.25em;
  }
}
</style>
