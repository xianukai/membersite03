<template>
  <div id="home">
    <v-container text-xs-center justify-center>
    <img src="@/assets/img/logo.png" alt="ロゴ">
    <v-layout row wrap>
      <v-flex xs12>
        <h1>会員サイト</h1>
        <p class="message">会員サイトをご利用の方は、Googleアカウントでログインしてください。</p>
      </v-flex>

      <v-flex xs12 mt-5>
        <v-btn color='info' @click="login">Googleアカウントでログイン</v-btn>
      </v-flex>
    </v-layout>
  </v-container>
  </div>
</template>

<script>
// @ is an alias to /src
import { mapActions } from 'vuex'

export default {
  methods: {
    ...mapActions(['login'])
  }
}
</script>

<style lang="scss">
body {
  color: #fff;
}

p {
  color: #fff;
}

h1 {
  color: #fff;
}

#home .message {
  color: #fff;
  font-size: 1rem;
}

@media screen and(max-width: 767px) {
  #home {
    .theme--light.v-btn:not(.v-btn--icon):not(.v-btn--flat) {
      max-width: 100%;
    }
  }
}



</style>