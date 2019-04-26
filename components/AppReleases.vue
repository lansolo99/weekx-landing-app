<template>
  <section class="appReleases">
    <v-container>
      <v-layout>
        <v-flex xs12>
          <h1 class="appReleases__title">Releases</h1>
        </v-flex>
      </v-layout>
      <v-layout justify-center>
        <v-flex xs9 class="appReleases__releasesList">
          <div
            v-for="release in releases"
            :key="release.date"
            class="release pa-4"
          >
            <v-layout>
              <v-flex xs13 class="release__title-col">
                <h2>{{ release.title }}</h2>
              </v-flex>
              <v-flex xs3 class="release__date-col">
                <span>{{ release.date }}</span>
              </v-flex>
            </v-layout>
            <v-layout>
              <v-flex xs12 class="release__changelog-col pt-3">
                <p class="mb-0">{{ release.changelog }}</p>
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
          title: 'v1.0.0-beta.1',
          date: '30 apr 2019',
          changelog:
            'Content of my first release. Learn how to set presentation through markdown file then.'
        },
        {
          title: 'v0.0.0-alpha.1',
          date: '01 mar 2019',
          changelog: 'Content of my very first release.'
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
  padding: 40px 0;

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
      p {
        opacity: 0.8;
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
