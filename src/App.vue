<template>
  <div class="App o-vertical-spacing o-vertical-spacing--xl">
    <div class="o-container o-container--s">
      <IntroText>
        <h1 slot="headline">
          Lazy Load Vue.js Components When They Become Visible
        </h1>
        Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy
        eirmod tempor invidunt ut labore et dolore magna.
      </IntroText>
    </div>

    <BannerImage>
      <img
        src="https://images.unsplash.com/photo-1515074060204-9be35bb919b3?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1280&h=400&q=80"
        src-set="https://images.unsplash.com/photo-1515074060204-9be35bb919b3?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=2560&h=800&q=20 2x"
        alt=""
      >
    </BannerImage>

    <div class="o-container">
      <MediaObject>
        <img src="" alt="" slot="image">
        <h2>Lorem Ipsum</h2>
        <p>
          Lorem Ipsum
        </p>
      </MediaObject>
    </div>

    <div class="o-container">
      <MediaObject>
        <img src="" alt="" slot="image">
        <h2>Dolor sit</h2>
        <p>
          Lorem Ipsum
        </p>
      </MediaObject>
    </div>

    <!-- TeaserGrid -->

    <!-- TextBox -->

    <!-- Footer -->
  </div>
</template>

<script>
import lazyLoadComponent from './utils/lazy-load-component';

// Initially load the BannerImage and IntroText components
// because they're immediately visible above the fold.
import BannerImage from './components/BannerImage.vue';
import IntroText from './components/IntroText.vue';
import SkeletonBox from './components/SkeletonBox.vue';

const defaultOptions = {
  loading: SkeletonBox,
  loadingData: {
    props: {
      width: `100%`,
      height: `20em`,
    },
  },
};

export default {
  name: `App`,
  components: {
    BannerImage,
    IntroText,
    MediaObject: lazyLoadComponent({
      ...defaultOptions,
      componentFactory: () => import(`./components/MediaObject.vue`),
    }),
  },
};
</script>

<style lang="scss">
@import './assets/scss/settings/**/*';
@import './assets/scss/generic/**/*';
@import '{
  .o-container,
  .o-container--s,
} from ~@avalanche/object-container';
@import '{
  .o-vertical-spacing,
  .o-vertical-spacing--xl,
} from ~@avalanche/object-vertical-spacing';

.App {
  padding-top: setting-spacing(xl);
  padding-bottom: setting-spacing(xl);
}
</style>
