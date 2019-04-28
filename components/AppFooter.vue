<template>
  <section class="appFooter">
    <v-container class="py-2">
      <v-layout>
        <v-flex xs12>
          <span class="appFooter__year">© 2019</span> -
          <a href="http://fr.linkedin.com/in/stephanechangarnier"
            >Stephane Changarnier</a
          >
          -
          <a href="https://lansolo.io">lansolo.io</a>
        </v-flex>
      </v-layout>
    </v-container>
  </section>
</template>

<script>
export default {}
</script>

<style lang="scss">
.appFooter {
  text-align: center;
  color: white;
  font-size: 14px;
  background-color: $color-matterhorn;

  a,
  &__year {
    display: inline-block;
    margin: 0 10px;
  }

  a {
    transition: color 0.15s;
    &:hover {
      color: white;
    }
  }
}
</style>
