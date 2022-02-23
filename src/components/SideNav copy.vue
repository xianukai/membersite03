<template>
  <div>
    <v-navigation-drawer v-model="$store.state.drawer" absolute temporary class="">
    <v-list class="pa-1">
      <v-list-tile avatar>
        <v-list-tile-avatar>
          <img v-if="photoURL" :src="photoURL">
        </v-list-tile-avatar>

        <v-list-tile-content>
          <v-list-tile-title>{{ userName }}</v-list-tile-title>
        </v-list-tile-content>
      </v-list-tile>
    </v-list>

    <v-list class="pt-0" dense>
      <v-divider></v-divider>

      <v-list-tile v-for="item in items" :key="item.title">
        <a :href="item.path">
          <v-list-tile-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-tile-action>

          <v-list-tile-content>
            <v-list-tile-title>{{ item.title }}</v-list-tile-title>
          </v-list-tile-content>

        </a>
      </v-list-tile>
      
    </v-list>
  </v-navigation-drawer>


    <nav>
      <ul>
        <li
          v-for="(item, i) in items"
          :key=i
        >
          {{ item.title }}
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'


export default {
  data () {
    return {
      items: [
        {
          title: 'トップ',
          icon: 'ondemand_video',
          link: {
            name: 'top'
          },
          path: '/top'
        },
        {
          title: '動画一覧', 
          icon: 'ondemand_video', 
          link: {
            name: 'video' 
          },
          path: '/video'
        },
        {
          title: 'サイトポリシー', 
          icon: 'list', 
          link: {
            name: 'policy'
          },
          path: '/policy'
        },
        {
          title: '設定', 
          icon: 'dialpad', 
          link: { 
            name: 'configpage'
          },
          path: '/configpage'
        },
      ]
    }
  },
  computed: {
    ...mapGetters(['userName', 'photoURL'])
  }
}
</script>

<style lang="scss">
.v-list__tile__content {
  font-size: 1.2rem;
}

.theme--light.v-navigation-drawer {
  position: fixed;
  background: #3f51b5;
}

.v-list__tile {
  color: #fff;
}

.v-list__tile a {
  display: flex;
  color: #fff;
  width: 100%;
}

.v-navigation-drawer > .v-list .v-list__tile--active .v-list__tile__title a {
  color: aquamarine;
}

.v-navigation-drawer > .v-list .v-list__tile--active .v-list__tile__title {
  color: aquamarine;
}
</style>