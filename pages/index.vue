<template>
  <div>
    <transition name="spinner">
      <AppSpinner v-show="showAppSpinner" />
    </transition>
    <AppHeader />
    <AppHero />
    <AppShowcase />
    <AppFeatures />
    <AppReleases />
    <AppFooter />
  </div>
</template>

<script>
import AppSpinner from '@/components/AppSpinner.vue'
import AppHeader from '@/components/AppHeader.vue'
import AppHero from '@/components/AppHero.vue'
import AppShowcase from '@/components/AppShowcase.vue'
import AppFeatures from '@/components/AppFeatures.vue'
import AppReleases from '@/components/AppReleases.vue'
import AppFooter from '@/components/AppFooter.vue'

export default {
  components: {
    AppSpinner,
    AppHeader,
    AppHero,
    AppShowcase,
    AppFeatures,
    AppReleases,
    AppFooter
  },
  head() {
    return {
      title: 'Weekx | Just a simple discipline app',
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        {
          hid: 'description',
          name: 'description',
          content:
            'Weekx is a weekly task planner web app focused on discipline and self-improvement. Try it now!'
        }
      ],
      link: [
        {
          rel: 'icon',
          type: 'image/x-icon',
          href: '/favicon.ico'
        },
        {
          rel: 'stylesheet',
          href:
            'https://fonts.googleapis.com/css?family=Signika+Negative:300,400,500,600'
        }
      ]
    }
  },
  data() {
    return {
      showAppSpinner: true
    }
  },
  mounted() {
    document.onreadystatechange = () => {
      if (document.readyState === 'complete') {
        this.showAppSpinner = false
      }
    }
  }
}
</script>

<style lang="scss">
.spinner-enter-active,
.spinner-leave-active {
  transition: opacity 0.3s ease-in-out;
}
.spinner-enter,
.spinner-leave-to {
  opacity: 0;
}
</style>
