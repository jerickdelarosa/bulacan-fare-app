<template>
  <q-table
    flat bordered
    :rows="props.content"
    :columns="columns"
    row-key="name"
    separator="vertical"
    :pagination="pagination"

  >
    <template v-slot:top>
      <div class="q-table__title">
        {{ props.startingLocation }} <q-icon name="east" /> {{ props.endingLocation }}
      </div>
    </template>

  </q-table>
</template>

<script setup>
import { ref } from 'vue'

const props = defineProps({
  startingLocation: String,
  endingLocation: String,
  content: Object
})

const columns = [
  {
    name: 'destination',
    required: true,
    label: 'Destination',
    align: 'center',
    field: 'destination',
    headerStyle: 'font-weight: bold',
    style: 'min-width: 180px;',
    sortable: true
  },
  {
    name: 'price',
    required: true,
    label: 'Price (PHP)',
    align: 'center',
    field: 'price',
    headerStyle: 'font-weight: bold',
    style: 'min-width: 100px;',
    sortable: true
  }
]

const pagination = ref({
  sortBy: 'desc',
  descending: false,
  page: 1,
  rowsPerPage: 10
})

</script>

<style lang="scss" scoped>

</style>
