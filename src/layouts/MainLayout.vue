<template>
  <q-layout view="hHh lpR fFf">

    <!-- <q-header class="bg-primary text-white"> -->
    <q-header elevated class="bg-white text-dark">
      <q-toolbar class="container-md q-py-md">
          <q-avatar size="md">
            <img src="../assets/bus.svg">
          </q-avatar>

          <q-toolbar-title class="text-weight-bold">Fare Matrix</q-toolbar-title>

        <!-- <q-btn flat round dense icon="home" /> -->
        <q-btn flat round dense :loading="backToHome" @click="goToHome()" icon="home">
          <template v-slot:loading>
            <q-spinner-facebook />
          </template>
        </q-btn>
      </q-toolbar>
    </q-header>

    <q-page-container class="bg-grey-2 ">
      <div>
        <router-view />
      </div>
      <!-- place QPageScroller at end of page -->
      <q-page-scroller position="bottom-right" :scroll-offset="150" :offset="[18, 18]">
        <q-btn fab square unelevated icon="keyboard_arrow_up" color="warning" />
      </q-page-scroller>

    </q-page-container>

    <q-footer class="bg-grey-1 text-dark">
      <q-toolbar class="flex flex-center text-center">
        <q-toolbar-title class="text-caption text-weight-medium">
          © 2023 All rights reserved.
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>

  </q-layout>
</template>

<script setup>
import { ref } from 'vue'
import { useRouter } from 'vue-router'

const backToHome = ref(false)

const router = useRouter()

const goToHome = () => {
  const currentPage = router.currentRoute.value.path
  console.log(currentPage)
  if (currentPage !== '/') {
    backToHome.value = true

    setTimeout(() => {
      router.push('/')
      backToHome.value = false
    }, 1000)
  }
}

</script>
