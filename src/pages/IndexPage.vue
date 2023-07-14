<template>
  <q-page class="flex flex-center">
    <q-card class="bg-grey-1 q-mt-xs" style="margin-top: -8rem" flat>
      <q-item class="q-my-lg">
        <q-item-section class="text-center">
          <q-item-label class="text-h4 q-ma-xs">Welcome to Fare Matrix</q-item-label>
          <q-item-label caption>where you can find location fares.</q-item-label>
        </q-item-section>
      </q-item>
      <q-card-actions class="text-center">
        <div class="q-gutter-md">
          <q-btn v-for="(link , index) in links" :key="`link-${link.id}`" :loading="loading[index]" color="accent" @click="simulateProgress(index)" style="width: 150px" outline>
            {{ link.title }}
            <template v-slot:loading>
              <q-spinner-hourglass class="on-left" />
              Loading...
            </template>
          </q-btn>
        </div>
      </q-card-actions>
    </q-card>
  </q-page>
</template>

<script setup>
import { ref } from 'vue'
import { navLinks } from '../constants/'

const links = ref(navLinks)

const loading = ref([
  false,
  false,
  false,
  false
])

// const progress = ref(false)

function simulateProgress (number) {
  // we set loading state
  loading.value[number] = true

  // simulate a delay
  setTimeout(() => {
    // we're done, we reset loading state
    loading.value[number] = false
  }, 3000)
}
</script>
