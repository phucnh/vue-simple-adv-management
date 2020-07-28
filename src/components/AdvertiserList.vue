<template>
  <v-container>
    <v-spacer />

    <v-flex xs12>
      <v-text-field clearable label="Advertiser Name" prepend-icon="mdi-filter-outline" v-model="filterText" />
    </v-flex>

    <v-flex xs12>
      <v-list>
        <v-subheader class="headline">Adveritsers</v-subheader>

        <v-spacer />

        <v-list-item v-for="(adv, index) in filteredAdvertisers" :key="index">
          <v-list-item-icon>
            <v-icon>mdi-account</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>
              {{ adv.name }}
              <p v-if="adv.deliveryStatus === 'on'">配信</p>
              <p v-else>停止</p>
            </v-list-item-title>
          </v-list-item-content>
          <v-btn color="red" dark icon @click="removeAdvertiser(adv.name)"><v-icon>mdi-delete</v-icon></v-btn>
        </v-list-item>
      </v-list>
    </v-flex>
  </v-container>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

type DeliveryStatus = 'on' | 'off';

interface Advertiser {
  name: string;
  deliveryStatus: DeliveryStatus;
}

@Component
export default class AdvertiserList extends Vue {
  readonly name = 'AdvertiserList';

  advertisers: Advertiser[] = [
    { name: 'Advertiser 1', deliveryStatus: 'on' },
    { name: 'Advertiser 2', deliveryStatus: 'on' },
    { name: 'Advertiser 3', deliveryStatus: 'off' },
    { name: 'Advertiser 4', deliveryStatus: 'on' },
    { name: 'Advertiser 5', deliveryStatus: 'off' },
    { name: 'Advertiser 6', deliveryStatus: 'on' },
  ];

  filterText = '';

  // computed properties
  get filteredAdvertisers(): Advertiser[] {
    if (this.filterText) {
      return this.advertisers.filter(adv => {
        return adv.name === this.filterText;
      });
    } else {
      return this.advertisers;
    }
  }

  removeAdvertiser(name: string) {
    this.advertisers = this.advertisers.filter(adv => {
      if (adv.name === name) return false;
      else return true;
    });
  }
}
</script>
