<template>
  <q-page class="bg-grey-2 flex flex-start">
    <div class="container-sm">
      <div class="q-mt-xs" flat>
        <div class="q-mb-lg q-mt-xl">
          <div>
            <q-item-label class="text-h5">Hagonoy, Bulacan</q-item-label>
            <q-item-label class="text-grey-500" body1>3002</q-item-label>
          </div>
        </div>

        <!-- Bus Fare -->
        <div>
          <q-card class="q-my-lg" flat bordered>
            <q-item>
              <q-item-section avatar>
                <q-avatar rounded size="md">
                  <img src="/src/assets/bus-chrome.svg">
                </q-avatar>
              </q-item-section>

              <q-item-section>
                <q-item-label class="text-h6">Bus fares</q-item-label>
              </q-item-section>
            </q-item>

            <q-separator />

            <q-card-section>
                <div class="row flex flex-wrap justify-center q-gutter-md">
                  <div class="col col-12 col-md-5">
                    <q-table
                      flat bordered
                      title="Hagonoy to Cubao"
                      :rows="busFares"
                      :columns="columns"
                      row-key="name"
                      separator="vertical"
                    />
                  </div>
                  <div class="col col-12 col-md-5">
                    <q-table
                      flat bordered
                      title="Cubao to Hagonoy"
                      :rows="busFares"
                      :columns="columns"
                      row-key="name"
                      separator="vertical"
                    />
                  </div>
                </div>
            </q-card-section>
          </q-card>
        </div>

        <!-- Jeep Fare -->
        <div>
          <q-card class="q-my-lg" flat bordered>
            <q-item>
              <q-item-section avatar>
                <q-avatar rounded size="md">
                  <img src="/src/assets/jeep.svg">
                </q-avatar>
              </q-item-section>

              <q-item-section>
                <q-item-label class="text-h6">Jeep fares</q-item-label>
              </q-item-section>
            </q-item>

            <q-separator />

            <q-card-section>
                <div class="row flex flex-wrap justify-center q-gutter-md">
                  <div class="col col-12 col-md-5">
                    <q-table
                      flat bordered
                      title="Hagonoy to Malolos"
                      :rows="jeepFares"
                      :columns="columns"
                      row-key="name"
                      separator="vertical"
                    />
                  </div>
                  <div class="col col-12 col-md-5">
                    <q-table
                      flat bordered
                      title="Malolos to Hagonoy"
                      :rows="jeepFares"
                      :columns="columns"
                      row-key="name"
                      separator="vertical"
                    />
                  </div>
                </div>
            </q-card-section>
          </q-card>
        </div>
      </div>
    </div>
  </q-page>
</template>

<script setup>
import { ref } from 'vue'
import { BusFares, JeepFares } from '../../constants/hagonoy-fares'

const busFares = ref(BusFares)
const jeepFares = ref(JeepFares)

const columns = [
  {
    name: 'destination',
    required: true,
    label: 'Destination',
    align: 'center',
    field: 'destination',
    sortable: true
  },
  {
    name: 'price',
    required: true,
    label: 'Price (PHP)',
    align: 'center',
    field: 'price',
    sortable: true
  }
]

</script>

<style scoped>

</style>
