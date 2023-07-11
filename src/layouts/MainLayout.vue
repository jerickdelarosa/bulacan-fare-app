<template>
  <q-layout view="hHh lpR fFf">

    <q-header class="bg-primary text-white">
      <q-toolbar class="container-md">
          <q-avatar size="md">
            <img src="../assets/bus.svg">
          </q-avatar>

          <q-toolbar-title>Fare Matrix</q-toolbar-title>

          <q-btn flat round dense icon="whatshot" />
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />

      <!-- place QPageScroller at end of page -->
      <q-page-scroller position="bottom-right" :scroll-offset="150" :offset="[18, 18]">
        <q-btn fab icon="keyboard_arrow_up" color="accent" />
      </q-page-scroller>

    </q-page-container>

    <q-footer class="bg-grey-8 text-white">
      <q-toolbar class="flex flex-center text-center">
        <q-toolbar-title class="text-caption">
          © 2023 All rights reserved.
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>

  </q-layout>
</template>

<script setup>

</script>
