<template>
  <section class="appReleases">
    <v-container>
      <v-layout>
        <v-flex xs12>
          <h1 class="appReleases__title">Releases</h1>
        </v-flex>
      </v-layout>
      <v-layout justify-center>
        <v-flex sm10 class="appReleases__releasesList">
          <div
            v-for="release in releases"
            :key="release.date"
            class="release pa-4"
          >
            <v-layout>
              <v-flex xs11 class="release__title-col">
                <h2>{{ release.title }}</h2>
              </v-flex>
              <v-flex xs5 class="release__date-col">
                <span>{{ release.date }}</span>
              </v-flex>
            </v-layout>
            <v-layout>
              <v-flex xs12 class="release__changelog-col pt-3">
                <ul>
                  <li v-for="item in release.changelog" :key="item.item">
                    {{ item.item }}
                  </li>
                </ul>
              </v-flex>
            </v-layout>
          </div>
        </v-flex>
      </v-layout>
    </v-container>
  </section>
</template>

<script>
export default {
  data() {
    return {
      releases: [
        {
          title: 'v1.0.0-beta',
          date: '30 apr 2019',
          changelog: [
            { item: "Added ellipsis to long task's name" },
            { item: 'Kill all notifications at midnight' }
          ]
        }
      ]
    }
  }
}
</script>

<style lang="scss">
.appReleases {
  text-align: center;
  position: relative;
  background-color: $color-blue;
  padding: 40px 0px 70px;

  &__title {
    color: $color-golden;
    font-size: 30px;
    font-weight: 400;
  }

  &__releasesList {
    margin-top: 40px;
  }
  .release {
    position: relative;
    background-color: rgba(black, 0.2);
    color: white;
    text-align: left;

    &:not(:first-child) {
      margin-top: 20px;
    }

    &__title-col {
      h2 {
        font-size: 22px;
        font-weight: 400;
      }
    }
    &__date-col {
      text-align: right;
      span {
        position: relative;
        top: 6px;
        opacity: 0.8;
      }
    }
    &__changelog-col {
      font-size: 16px;
      opacity: 0.8;
      li:not(:first-child) {
        margin-top: 5px;
      }
    }
    &:before {
      content: '';
      display: block;
      width: 5px;
      height: 22px;
      background-color: $color-green;
      position: absolute;
      top: 30px;
      left: 0;
    }
  }
}
</style>
