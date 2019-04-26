<template>
  <section class="appShowCase">
    <div class="appElements">
      <h1 class="appElements__title">
        A simple discipline <br />habits tracker
      </h1>
      <div class="appElements__phone">
        <img
          src="~assets/images/phone_back.svg"
          class="appElements__phone-mockup appElements__phone-mockup--back"
        />
        <video
          src="~assets/images/screencast.mp4"
          width="238"
          height="489"
          autoplay="1"
          type="video/mp4"
        />
        <img
          src="~assets/images/phone_body.svg"
          class="appElements__phone-mockup appElements__phone-mockup--front"
        />
      </div>
      <div class="appElements__description">
        <v-btn @click="playTheVid">launch</v-btn>
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
        <a href="http://www.weekx.xyz">
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
    return {}
  },
  mounted() {
    // Screencast control
    const media = document.querySelector('video')
    media.loop = true

    document.onreadystatechange = () => {
      if (document.readyState === 'complete') {
        // run code here
        console.log('loaded')
        const playPromise = media.play()
        if (playPromise !== undefined) {
          playPromise
            .then(() => {
              media.play()
              console.log('Automatic playback started!')
            })
            .catch(error => {
              // media.play()
              console.log('Auto-play was prevented')
              console.log(error)
            })
        }
      }
    }
    // window.addEventListener('DOMContentLoaded', function(event) {

    // })

    // media.loop = true
    // media.load()
    // fetchVideoAndPlay()
    // // Video fetch
    // function fetchVideoAndPlay() {
    //   fetch(require('~/assets/images/screencast.mp4'))
    //     .then(response => {
    //       console.log(response)
    //       response.blob()
    //     })
    //     .then(blob => {
    //       media.srcObject = blob
    //       return media.play()
    //     })
    //     .then(_ => {
    //       console.warn('video playback started')
    //     })
    //     .catch(e => {
    //       console.warn(e)
    //       console.warn('Video playback failed')
    //     })
    // }
  },
  methods: {
    playTheVid() {
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

    @include responsive(mobile) {
      width: 100%;
      margin-top: 60px;
      padding-left: 30px;
      padding-right: 30px;
    }

    &__title {
      font-size: 3.75rem;
      font-weight: 6s00;
      line-height: 4.7rem;

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

      @include responsive(mobile) {
        margin-top: 60px;
      }

      video {
        position: relative;
        top: 46px;
        left: 0px;
        width: 238px;
        height: 489px;
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
    &__description {
      margin-top: 50px;
      font-weight: 300;
      font-size: 20px;
    }
    &__btn-pwa {
      img {
        transition: all 200ms cubic-bezier(0.175, 0.885, 0.32, 1.275);
      }
      a {
        display: block;
        margin: auto;
        width: 190px;
        padding-top: 40px;
        img {
          &:hover {
            transform: scale(1.1);
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
