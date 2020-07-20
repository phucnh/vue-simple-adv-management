<template>
  <v-container>
    <v-spacer />

    <!-- <v-flex xs12>
      <v-text-field clearable label="Advertiser Name" prepend-icon="mdi-filter-outline" v-bind:value="filterText" />
    </v-flex> -->

    <v-flex xs12>
      <v-list>
        <v-subheader class="headline">Adveritsers</v-subheader>

        <v-spacer />

        <v-list-item v-for="adv in advertisers" :key="adv.name">
          <v-list-item-icon>
            <v-icon>mdi-account</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title v-text="adv.name"></v-list-item-title>
          </v-list-item-content>
          <!-- <v-btn color="red" dark icon @click="removeAdvertiser(index)"><v-icon>mdi-delete</v-icon></v-btn> -->
        </v-list-item>
      </v-list>
    </v-flex>
  </v-container>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

interface Advertiser {
  name: string;
}

@Component
export default class AdvertiserList extends Vue {
  readonly name = 'AdvertiserList';

  advertisers: Advertiser[] = [];
  // [
  //   { name: 'Advertiser 1' },
  //   { name: 'Advertiser 2' },
  //   { name: 'Advertiser 3' },
  //   { name: 'Advertiser 4' },
  //   { name: 'Advertiser 5' },
  //   { name: 'Advertiser 6' },
  // ];

  // filterText = 'advertiser 2';

  // computed properties
  // get filteredAdvertisers(): Advertiser[] {
  // TODO: write filter logic
  // }

  // removeAdvertiser(index: number) {
  // TODO: write remove logic
  // }
}
</script>
