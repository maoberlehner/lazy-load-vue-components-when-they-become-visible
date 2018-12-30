<template>
  <div class="App o-vertical-spacing o-vertical-spacing--xl">
    <div class="o-container o-container--s">
      <IntroText>
        <h1 slot="headline">
          Lazy Load Vue.js Components When They Become Visible
        </h1>
        The following sections of this page (except the very next banner image)
        are lazy loaded as soon as they become visible.
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
        <img
          slot="image"
          src="https://images.unsplash.com/photo-1510151490593-aa277bc49f37?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=400&h=300&q=80"
          src-set="https://images.unsplash.com/photo-1510151490593-aa277bc49f37?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&h=600&q=20 2x"
          alt=""
        >
        <div class="s-content">
          <h2>Lorem Ipsum</h2>
          <p>
            Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam
            nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam
            erat, sed diam voluptua.
          </p>
          <p>
            Consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt
            ut labore et dolore magna aliquyam erat, sed diam voluptua.
          </p>
        </div>
      </MediaObject>
    </div>

    <div class="o-container">
      <MediaObject>
        <img
          slot="image"
          src="https://images.unsplash.com/photo-1509904446473-1b8b71534223?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=400&h=300&q=80"
          src-set="https://images.unsplash.com/photo-1509904446473-1b8b71534223?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&h=600&q=20 2x"
          alt=""
        >
        <div class="s-content">
          <h2>Dolor sit</h2>
          <p>
            Consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt
            ut labore et dolore magna aliquyam erat, sed diam voluptua.
          </p>
          <p>
            Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam
            nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam
            erat, sed diam voluptua.
          </p>
        </div>
      </MediaObject>
    </div>

    <div class="o-container">
      <TeaserGrid/>
    </div>

    <div class="o-container">
      <MarkdownText
        :md="markdown"
      />
    </div>
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
    MarkdownText: lazyLoadComponent({
      ...defaultOptions,
      componentFactory: () => import(`./components/MarkdownText.vue`),
    }),
    MediaObject: lazyLoadComponent({
      ...defaultOptions,
      componentFactory: () => import(`./components/MediaObject.vue`),
    }),
    TeaserGrid: lazyLoadComponent({
      ...defaultOptions,
      componentFactory: () => import(`./components/TeaserGrid.vue`),
    }),
  },
  created() {
    this.markdown = `
## Lorem Ipsum

Consetetur sadipscing elitr, **sed diam nonumy** eirmod tempor invidunt
ut labore et *dolore* magna aliquyam erat, sed diam voluptua.
    `;
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
  .o-grid,
} from ~@avalanche/object-grid';
@import '{
  .o-vertical-spacing,
  .o-vertical-spacing--xl,
} from ~@avalanche/object-vertical-spacing';
@import '{
  .u-width-12\/12,
  .u-width-4\/12\@s,
} from ~@avalanche/utility-width';

.s-content {
  * + * {
    margin-top: setting-spacing(m);
  }

  em {
    font-style: italic;
  }

  strong {
    font-weight: bold;
  }
}

.App {
  padding-top: setting-spacing(xl);
  padding-bottom: setting-spacing(xl);
}
</style>
