<template>
  <section class="appHeader">
    <v-container class="pt-4 pb-0">
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
              <v-btn href="https://github.com/lansolo99/weekx" flat
                >Github</v-btn
              >
              <v-btn
                href="mailto:feedback@weekx.xyz?subject=Feedback%20on%20Weekx"
                flat
                >Feedbacks</v-btn
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

    @include responsive(mobile) {
      .v-toolbar__content {
        display: block;
        padding: 20px;
      }
    }

    .v-btn {
      @include responsive(mobile) {
        display: none;
      }

      &:hover {
        background-color: $color-blue;
        color: white;
      }
    }
  }

  &__logo {
    width: 105px;
    @include responsive(mobile) {
      display: block;
      width: 105px;
      margin: auto !important;
    }
  }
}
</style>
