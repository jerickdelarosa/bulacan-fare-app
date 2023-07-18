<template>
  <q-page class="container row flex justify-center q-px-xl">
    <div class="q-mt-md q-mb-lg" flat>
      <div class="col col-12">
        <q-item>
          <q-item-section class="flex items-center" style="flex-direction: row">
            <q-avatar class="d-inline">
              <q-icon name="location_on" size="md" color="warning" />
            </q-avatar>
            <q-item-label class="text-h6">Hagonoy, Bulacan</q-item-label>
          </q-item-section>
        </q-item>

        <!-- BUS FARE -->
        <q-card flat>
          <q-item>
            <q-item-section avatar>
              <q-avatar rounded size="lg">
                <img src="/src/assets/bus-green.svg">
              </q-avatar>
            </q-item-section>

            <q-item-section>
              <q-item-label class="text-h6">Bus fares</q-item-label>
            </q-item-section>
          </q-item>

          <q-separator inset />

          <q-card-section>
            <div class="row q-col-gutter-md">
                <div class="col col-12 col-md-6 ">
                    <FareTable
                      starting-location="Hagonoy"
                      ending-location="Cubao"
                      :content="busFares"
                    />
                </div>
                <div class="col col-12 col-md-6">
                    <FareTable
                      starting-location="Cubao"
                      ending-location="Hagonoy"
                      :content="busFares"
                    />
                </div>
              </div>
          </q-card-section>
        </q-card>

        <!-- JEEP FARE -->
        <q-card class="q-mt-md" flat>
          <q-item>
            <q-item-section avatar>
              <q-avatar rounded size="lg">
                <img src="/src/assets/jeep-yellow.svg">
              </q-avatar>
            </q-item-section>

            <q-item-section>
              <q-item-label class="text-h6">Jeep fares</q-item-label>
            </q-item-section>
          </q-item>

          <q-separator inset />

          <q-card-section>
            <div class="row q-col-gutter-md">
                <div class="col col-12 col-md-6">
                    <FareTable
                      starting-location="Hagonoy"
                      ending-location="Malolos"
                      :content="jeepFares"
                    />
                </div>
                <div class="col col-12 col-md-6">
                    <FareTable
                      starting-location="Malolos"
                      ending-location="Hagonoy"
                      :content="jeepFares"
                    />
                </div>
              </div>
          </q-card-section>
        </q-card>
      </div>
    </div>
  </q-page>
</template>

<script setup>
import { ref } from 'vue'
import { BusFares, JeepFares } from '../../constants/hagonoy-fares'
import FareTable from '../../components/FareTable.vue'

const busFares = ref(BusFares)
const jeepFares = ref(JeepFares)

</script>

<style scoped>

</style>
