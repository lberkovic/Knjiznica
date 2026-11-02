<template>
  <q-page padding>
    <h4>Pretraživanje knjiga</h4>

    <q-input
      v-model="searchText"
      label="Unesite naziv knjige ili autora"
      outlined
    />
    <q-option-group
    v-model="searchType"
    :options="
    [
    { label: 'Naziv knjige', value: 'name' },
    { label: 'Autor', value: 'author' }
    ]"
    type="radio"
    />
    <q-btn
      label="Pretraži"
      color="primary"
      class="q-mt-md"
      @click="searchBooks"
    />
    <q-table
    class="q-mt-lg"
    title="Rezultati pretraživanja"
    :rows="filteredRows"
    :columns="columns"
    row-key="name"
    />
  </q-page>
</template>

<script setup>
import { ref } from 'vue'

const searchText = ref('')
const searchType = ref('name')
const columns = [
  {
    name: 'id',
    label: 'ID',
    field: 'id',
    align: 'left'
  },
  {
    name: 'name',
    label: 'Naziv knjige',
    field: 'name',
    align: 'left'
  },
  {
    name: 'author',
    label: 'Autor',
    field: 'author',
    align: 'left'
  },
  {
    name: 'year',
    label: 'Godina izdanja',
    field: 'year',
    align: 'left'
  },
  {
    name: 'izdavac',
    label: 'Izdavač',
    field: 'izdavac',
    align: 'left'
  }
]

const rows = [
  { id: 1, name: 'Mali princ', author: 'Antoine de Saint-Exupéry', year: 1943, izdavac: "Mladost"},
  { id: 2, name: 'Zločin i kazna', author: 'Fjodor Dostojevski', year: 1866, izdavac: "Školska knjiga" },
  { id: 3, name: 'Proces', author: 'Franz Kafka', year: 1925, izdavac: "Naklada Ljevak" },
  { id: 4, name: 'Na Drini ćuprija', author: 'Ivo Andrić', year: 1945, izdavac: "Prosveta" },
  { id: 5, name: 'Ponos i predrasude', author: 'Jane Austen', year: 1813, izdavac: "Znanje" }
]

const filteredRows = ref([])

function searchBooks() {
  filteredRows.value = rows.filter((book) =>
    book[searchType.value]
      .toLowerCase()
      .includes(searchText.value.toLowerCase())
  )
}
</script>