<template>
  <q-page class="flex flex-center">
    <div class="q-mt-xs" style="margin-top: -8rem" flat>
      <div class="q-my-lg justify-center">
        <q-item-section class="text-center">
          <q-item-label class="text-h4 q-ma-xs">Welcome to Fare Matrix</q-item-label>
          <q-item-label caption>where you can find destination fares.</q-item-label>
        </q-item-section>
      </div>
      <div class="flex flex-wrap justify-center q-pa-1">
        <div class="flex justify-center q-gutter-md">
          <q-btn
          v-for="(link , index) in links"
          :key="`link-${link.id}`"
          :loading="loading[index]"
          @click="simulateProgress(link.to, index)"
          style="width: 150px"
          outline
          >
            {{ link.title }}
            <template v-slot:loading>
              <q-spinner-facebook />
            </template>
          </q-btn>
        </div>
      </div>
    </div>
  </q-page>
</template>

<script setup>
import { ref } from 'vue'
import { navLinks } from '../constants/'
import { useRouter } from 'vue-router'

const links = ref(navLinks)

const router = useRouter()

const loading = ref([
  false,
  false,
  false,
  false
])

function simulateProgress (link, number) {
  // we set loading state
  loading.value[number] = true

  // simulate a delay
  setTimeout(() => {
    router.push(link)
    // we're done, we reset loading state
    loading.value[number] = false
  }, 1000)
}
</script>
