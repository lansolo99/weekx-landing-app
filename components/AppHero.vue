<template>
  <section class="appHero">
    <div class="hero">
      <no-ssr>
        <parallax :speed-factor="0.3">
          <img src="~assets/images/desktop@2x.jpg" alt="Weekx theme" />
        </parallax>
      </no-ssr>
    </div>
  </section>
</template>

<script>
import Parallax from 'vue-parallaxy'

export default {
  components: {
    Parallax
  },
  data() {
    return {}
  }
}
</script>

<style lang="scss">
.appHero {
  position: absolute;
  top: 0;
  left: 0;
  display: block;
  width: 100%;
  height: 820px;
  background-color: $color-golden;

  // Parallaxy

  @media screen and (min-width: 768px) {
    .Masthead {
      height: 800px !important;
      min-height: 0 !important;
    }
  }

  @media screen and (max-width: 768px) {
    .Masthead {
      height: 500px !important;
      min-height: 0 !important;
    }
  }

  .Masthead {
    z-index: 0;
  }
  .hero {
    position: relative;
    //height: 820px;
    background-color: $color-golden;
    clip-path: polygon(0% 0%, 100% 0%, 100% 80%, 0% 100%);
  }
}
</style>
