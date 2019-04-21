<template>
  <section class="appFeatures">
    <v-container>
      <v-layout>
        <v-flex md4 class="red pa-4 appFeatures__column">
          <img
            src="~assets/images/appFeatures_habits.svg"
            alt="Create your habits"
          />
          <h1 class="">Create your habits</h1>
          <p>
            Set tasks, define a schedule among weekly options (everydays, x
            times a week, specific days or single tasks).
          </p>
        </v-flex>
        <v-flex md4 class="green">
          col
        </v-flex>
        <v-flex md4 class="blue">
          col
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
  background-color: green;
  padding-top: 40px;

  &__column {
    text-align: center;
    img {
      width: 70px;
    }

    h1 {
      font-size: 25px;
      font-weight: 500;
    }
    p {
      font-weight: 300;
      font-size: 18px;
    }
  }
}
</style>
