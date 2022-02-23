<template>
  <div id="top">
    <div class="inner">
      <TextAnime1/>
      <p class="center greet">
        ようこそ
        <span>{{ userName }}</span>
        さん
      </p>
      <v-toolbar-items v-if="$store.state.login_user">
        <v-btn>
          <a href="/video">動画一覧へ</a>
        </v-btn>
      </v-toolbar-items>
    </div>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'
import TextAnime1 from '@/components/TextAnime1'

export default {
  components: {
    TextAnime1,
  },
  computed: {
    ...mapGetters(['userName'])
  }
}
</script>

<style lang="scss">
.center {
  text-align: center;
}

.greet {
  font-size: 1.6rem;

  span {
    color: orange;
  }
}

.message {
  margin-bottom: 40px;
  color: #fff;
  font-size: 3rem;
  font-family: 'Arial';
  font-weight: normal;
}

.v-content {
  background-image: url(../assets/img/bg01.jpg);
  // background-size: cover;
  // background-repeat: repeat-y;
  background-color: #000;
  position: relative;

  &::after {
    content: "";
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    background-color: rgba(37, 46, 53, 0.7);
    z-index: 0;
  }
}

.v-content__wrap {
  z-index: 1;
}

#top {
  z-index: 99;

  .v-btn {
    padding: 0 0;
    margin: 0 auto;
  }
  .v-toolbar__items {
    min-width: 200px;
    width: 300px;
    margin: 0 auto;

    a {
      color: #fff;
      display: block;
      width: 100%;
      padding: 16px 16px;
      letter-spacing: 0.2rem;
      font-size: 1.4rem;
    }
  }
}

.column {
  margin-bottom: 4rem;
}

.heading {
  &__lv2 {
    font-size: 3rem;
    margin-bottom: 2rem;
  }
  &__lv3 {
    font-size: 2rem;
    margin-bottom: 2rem;

    // &:before {
    //   content: "";
    //   border-left: 5px solid orange;
    //   margin-right: 10px;
    // }
  }
}

.small {
  font-size: 1.4rem;
}

video {
  width: 600px;
}

.tag__area {
  display: flex;
  margin: 20px 0;

  .tag {
    color: #fff;
    padding: 4px 8px;
    border-radius: 4px;
    margin-right: 10px;
  }
}

@media screen and (max-width: 767px) {
  #top .theme--light.v-btn:not(.v-btn--icon):not(.v-btn--flat) {
    max-width: 100%;
  }
}
</style>