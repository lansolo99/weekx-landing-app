<template>
  <div>
    <TheHeader />
    <AppHero />
    <AppShowcase />
  </div>
</template>

<script>
import TheHeader from '@/components/TheHeader.vue'
import AppHero from '@/components/AppHero.vue'
import AppShowcase from '@/components/AppShowcase.vue'

export default {
  components: {
    TheHeader,
    AppHero,
    AppShowcase
  },
  head() {
    return {
      title: 'Weekx',
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        {
          hid: 'description',
          name: 'description',
          content: 'My custom description'
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
  }
}
</script>
