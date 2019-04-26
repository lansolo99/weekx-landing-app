<template>
  <section class="appHeader">
    <v-container class="pt-3 pb-0">
      <v-layout>
        <v-flex>
          <v-toolbar absolute flat class="appHeader__toolbar transparent">
            <img
              class="appHeader__logo"
              src="~assets/images/logo.svg"
              alt="Weekx"
            />
            <v-spacer></v-spacer>
            <v-toolbar-items>
              <v-btn flat>Twitter</v-btn>
              <v-btn
                href="mailto:feedback@weekx.xyz?subject=Feedback%20on%20Weekx"
                flat
                >Insult me</v-btn
              >
            </v-toolbar-items>
          </v-toolbar>
        </v-flex>
      </v-layout>
    </v-container>
  </section>
</template>

<script>
export default {}
</script>

<style lang="scss">
.appHeader {
  position: relative;

  @media only screen and (min-width: 960px) {
    .container {
      max-width: none;
    }
  }

  &__toolbar {
    max-width: 2000px;
    margin: auto;
    position: relative;
  }

  &__logo {
    width: 86px;
  }
}
</style>
