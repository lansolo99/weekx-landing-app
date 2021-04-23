<template>
  <section class="appShowCase">
    <div class="appElements">
      <h1 class="appElements__title">
        Just a simple discipline App
      </h1>
      <div
        class="appElements__phone"
        :class="{ videoPlay: videoPlay }"
        @click="playTheVid"
      >
        <img
          src="~assets/images/phone_back.svg"
          class="appElements__phone-mockup appElements__phone-mockup--back"
        />
        <video
          src="~assets/images/screencast.mp4"
          width="239"
          height="490"
          preload
          playsinline
          muted
          loop
          type="video/mp4"
        />
        <div v-if="!videoPlay" class="appElements__beforePlayPreview">
          <img
            src="~assets/images/screencast_preview.jpg"
            srcset="
              ~assets/images/screencast_preview.jpg    1x,
              ~assets/images/screencast_preview@2x.jpg 2x
            "
            alt="weekx screencast preview"
          />
        </div>
        <div v-if="!videoPlay" class="appElements__beforePlayLayer"></div>

        <img
          src="~assets/images/phone_body.svg"
          class="appElements__phone-mockup appElements__phone-mockup--front"
        />

        <img
          v-if="!videoPlay"
          class="appElements__beforePlayBtn"
          src="~assets/images/phone_play.svg"
        />
      </div>
      <div class="appElements__description">
        <p>
          Weekx is a weekly task planner web app focused on self-improvement.
          It’s made for people who want to track their discipline commitment.
          Set tasks, define schedules, check when it’s done, track your
          progression.
        </p>
        <p>
          Keep up with a high discipline level everyday!
        </p>
      </div>
      <div class="appElements__btn-pwa">
        <a href="https://weekx-app.netlify.app/">
          <img src="~assets/images/btn-pwa.svg" alt="pwa button" />
        </a>
        <p class="appElements__btn-pwa-legend">Best viewed on mobile devices</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      videoPlay: false
    }
  },
  methods: {
    playTheVid() {
      // Remove beforePlayLayer
      this.videoPlay = true

      // Play video
      const media = document.querySelector('video')
      media.loop = true
      media.play()
    }
  }
}
</script>

<style lang="scss">
.appShowCase {
  background-color: $color-golden;
  padding-bottom: 40px;

  .appElements {
    margin: auto;
    display: block;
    text-align: center;
    width: 500px;
    position: relative;
    margin: auto;
    margin-top: 80px;
    @include textSelection;

    @include responsive(mobile) {
      width: 100%;
      margin-top: 60px;
      padding-left: 30px;
      padding-right: 30px;
    }

    &__title {
      font-size: 3.75rem;
      font-weight: 600;
      line-height: 4.7rem;
      @include textSelection;

      @include responsive(mobile) {
        font-size: 2.6rem;
        line-height: 3rem;
      }
    }
    &__phone {
      position: relative;
      margin: auto;
      margin-top: 70px;
      width: 265px;
      height: 541px;
      cursor: pointer;

      &.videoPlay {
        cursor: default;
      }

      &:hover {
        .appElements__beforePlayBtn {
          transform-origin: center;
          transform: translateY(-50%) translateX(-50%) scale(1.1);
        }
      }

      @include responsive(mobile) {
        margin-top: 60px;
      }

      video {
        position: relative;
        top: 46px;
        // left: 0px;
        // width: 238px;
        // height: 489px;

        left: -1px;
        width: 239px;
        height: 490px;
      }
      &-mockup {
        display: block;
        position: absolute;
        width: 265px;
        top: 0;
        left: 0;
        &--back {
          filter: drop-shadow(0px 0px 3px rgba(0, 0, 0, 0.5));
        }
      }
    }

    &__beforePlayPreview {
      position: absolute;
      top: 46px;
      left: 13px;
      width: 238px;
      height: 489px;
      img {
        display: block;
      }
    }

    &__beforePlayLayer {
      background-color: $color-golden;
      opacity: 0.4;
      background-blend-mode: lighten;
      position: absolute;
      top: 46px;
      left: 13px;
      width: 238px;
      height: 489px;
    }

    &__beforePlayBtn {
      position: absolute;
      width: 67px;
      height: 67px;
      top: 50%;
      transform: translateY(-50%) translateX(-50%);
      left: 50%;
      filter: drop-shadow(0px 0px 2px rgba(0, 0, 0, 0.3));
      transition: all 200ms cubic-bezier(0.175, 0.885, 0.32, 1.275);
    }

    &__description {
      margin-top: 50px;
      font-weight: 300;
      font-size: 20px;
      @include textSelection;
    }
    &__btn-pwa {
      img {
        transition: all 200ms cubic-bezier(0.175, 0.885, 0.32, 1.275);
      }
      a {
        display: block;
        margin: auto;
        width: 170px;
        padding-top: 40px;
        img {
          &:hover {
            transform: scale(1.05);
          }
        }
      }
      &-legend {
        font-weight: 300;
        font-size: 14px;
        font-style: italic;
        margin-bottom: 0;
      }
    }
  }
}
</style>
