<template>
  <v-app>
    <v-main>
      <v-container>
        <v-layout row justify-center class="ma-5">
          <v-flex xs12 sm8>
            <v-toolbar color="blue draken-4" dark>
              <v-app-bar-nav-icon></v-app-bar-nav-icon>
              <v-toolbar-title class="headline">Advertiser Manage App</v-toolbar-title>
            </v-toolbar>

            <AdvertiserList />
          </v-flex>
        </v-layout>
      </v-container>
    </v-main>
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue';
import AdvertiserList from '@/components/AdvertiserList.vue';

export default Vue.extend({
  name: 'App',

  components: {
    AdvertiserList,
  },

  data: () => ({
    //
  }),
});
</script>
