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
  }
}
</script>
