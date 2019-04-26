<template>
  <section class="appFeatures">
    <v-container class="pt-0">
      <v-layout wrap>
        <v-flex
          sm12
          md4
          class="appFeatures__column"
          :class="{
            'py-4 px-5': $vuetify.breakpoint.smAndDown,
            'py-2 px-5': $vuetify.breakpoint.mdAndUp
          }"
        >
          <img
            src="~assets/images/appFeatures_habits.svg"
            alt="Create your habits"
          />
          <h1 class="">Create your habits</h1>
          <p class="appFeatures__column-description">
            Set tasks, define a schedule among weekly options (everydays, x
            times a week, specific days or single tasks).
          </p>
        </v-flex>
        <v-flex
          sm12
          md4
          class="appFeatures__column"
          :class="{
            'py-4 px-5': $vuetify.breakpoint.smAndDown,
            'py-2 px-5': $vuetify.breakpoint.mdAndUp
          }"
        >
          <img
            src="~assets/images/appFeatures_progression.svg"
            alt="Track your progression"
          />
          <h1 class="">Track your progression</h1>
          <p class="appFeatures__column-description">
            Level-up your commitment to 100% on a 10 weeks range. Completion
            records are also available by-task.
          </p>
        </v-flex>
        <v-flex
          sm12
          md4
          class="appFeatures__column"
          :class="{
            'py-4 px-5': $vuetify.breakpoint.smAndDown,
            'py-2 px-5': $vuetify.breakpoint.mdAndUp
          }"
        >
          <img
            src="~assets/images/appFeatures_reminder.svg"
            alt="Set a daily reminder"
          />
          <h1 class="">Set a daily reminder</h1>
          <p class="appFeatures__column-description">
            Activate notifications for your task(s) due today and choose a time
            that fit your schedule.
          </p>
        </v-flex>
      </v-layout>
    </v-container>
  </section>
</template>

<script>
export default {}
</script>

<style lang="scss">
.appFeatures {
  position: relative;
  background-color: $color-golden;
  padding-top: 40px;
  padding-bottom: 40px;

  &__column {
    text-align: center;
    img {
      width: 70px;
    }

    h1 {
      margin-top: 10px;
      font-size: 25px;
      font-weight: 500;
    }
    &-description {
      @include responsive(tablet) {
        // padding-left: 4rem;
        // padding-right: 4rem;
        max-width: 500px;
      }
      margin: auto;
      margin-top: 20px;
      font-weight: 300;
      font-size: 18px;
    }
  }
}
</style>
