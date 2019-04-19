<template>
  <div class="appShowCase">
    <div class="appElements">
      <h1 class="appElements__title">A simple discipline habits tracker</h1>
      <div class="appElements__phone">
        <img
          src="~assets/images/phone_back.svg"
          class="appElements__phone-mockup appElements__phone-mockup--back"
        />
        <video
          src="~assets/images/screencast.mp4"
          width="238"
          height="489"
          type="video/mp4"
        />
        <img
          src="~assets/images/phone_body.svg"
          class="appElements__phone-mockup appElements__phone-mockup--front"
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
    </div>
    <div class="sep"></div>
  </div>
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
    media.load()
    fetchVideoAndPlay()
    // Video fetch
    function fetchVideoAndPlay() {
      // fetch(require('~/assets/images/screencast.mp4'))
      fetch(require('~/assets/images/screencast.mp4'))
        .then(response => {
          response.blob()
        })
        .then(blob => {
          media.srcObject = blob
          return media.play()
        })
        .then(_ => {
          console.warn('video playback started')
        })
        .catch(e => {
          console.warn('Video playback failed')
        })
    }

    // Local fetch exemple
    // fetch(require('~/assets/images/screencast.mp4'))
    //   .then(response => {
    //     console.warn(response)
    //     console.log('file ok')
    //   })
    //   .catch(error => {
    //     console.log(error)
    //   })

    // Basic Fetch exemple
    // fetch('https://jsonplaceholder.typicode.com/todos/1')
    //   .then(response => {
    //     response.json().then(posts => {
    //       console.log(posts)
    //     })
    //   })
    //   .catch(error => {
    //     console.log(error)
    //   })
  }
}
</script>

<style lang="scss">
.appShowCase {
  background-color: $color-golden;

  .appElements {
    margin: auto;
    display: block;
    text-align: center;
    width: 500px;
    position: absolute;
    top: 180px;
    left: 50%;
    transform: translateX(-50%);

    &__title {
      font-size: 3.75rem;
      font-weight: 500;
      line-height: 4.7rem;
    }
    &__phone {
      position: relative;
      margin: auto;
      margin-top: 70px;
      width: 265px;
      height: 541px;
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
  }

  .sep {
    background-color: $color-golden;
    height: 1200px;
  }
}
</style>
