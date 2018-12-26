<template>
  <div class="TeaserGrid o-grid">
    <div class="o-grid__item u-width-12/12 u-width-4/12@s">
      <div class="TeaserGrid__item">
        <img
          src="https://images.unsplash.com/photo-1515590575353-3cb9aaed5600?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=318&h=180&q=80"
          src-set="https://images.unsplash.com/photo-1515590575353-3cb9aaed5600?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=636&h=360&q=20 2x"
          alt=""
        >
        <div class="TeaserGrid__item-body s-content">
          <h3>Lorem Ipsum</h3>
          <p>
            Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam
            nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam
            erat, sed diam voluptua.
          </p>
        </div>
      </div>
    </div>
    <div class="o-grid__item u-width-12/12 u-width-4/12@s">
      <div class="TeaserGrid__item">
        <img
          src="https://images.unsplash.com/photo-1513370451437-6815b37b5cdc?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=318&h=180&q=80"
          src-set="https://images.unsplash.com/photo-1513370451437-6815b37b5cdc?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=636&h=360&q=20 2x"
          alt=""
        >
        <div class="TeaserGrid__item-body s-content">
          <h3>Dolor Ipsum</h3>
          <p>
            Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam
            nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam
            erat, sed diam voluptua.
          </p>
        </div>
      </div>
    </div>
    <div class="o-grid__item u-width-12/12 u-width-4/12@s">
      <div class="TeaserGrid__item">
        <img
          src="https://images.unsplash.com/photo-1448724133127-81fbec83d1ae?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=318&h=180&q=80"
          src-set="https://images.unsplash.com/photo-1448724133127-81fbec83d1ae?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=636&h=360&q=20 2x"
          alt=""
        >
        <div class="TeaserGrid__item-body s-content">
          <h3>Sit Lorem</h3>
          <p>
            Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam
            nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam
            erat, sed diam voluptua.
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: `TeaserGrid`,
};
</script>

<style lang="scss">
@import '../assets/scss/settings/**/*';

.TeaserGrid__item {
  border: 1px solid #e2e2e2;
  border-radius: 0.1875em;
}

.TeaserGrid__item-body {
  padding: setting-spacing(m);
}
</style>
