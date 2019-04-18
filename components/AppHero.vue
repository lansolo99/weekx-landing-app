<template>
  <div class="appHero">
    <div class="hero">
      <no-ssr>
        <parallax :speed-factor="0.3">
          <img src="~assets/images/desktop@2x.jpg" alt="Weekx theme" />
        </parallax>
      </no-ssr>
    </div>
  </div>
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
  background-color: $color-golden;

  .Masthead {
    z-index: 0;
  }
  .hero {
    position: relative;
    height: 820px;
    background-color: $color-golden;
    clip-path: polygon(0% 0%, 100% 0%, 100% 80%, 0% 100%);
  }
}
</style>
