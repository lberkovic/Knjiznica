<template>
  <q-page class="q-pa-md">
    <q-card dark bordered class="bg-grey-9 my-card">
      <q-card-section>
        <div class="text-h3 text-weight-bolder text-center">
          Popis svih knjiga
        </div>
      </q-card-section>

      <q-card-section class="text-h4 text-justify">
        {{ popis_knjiga }}
      </q-card-section>

      <q-card-section>
        <q-table
          title="Knjige"
          :rows="rows"
          :columns="columns"
          row-key="id"
        />
      </q-card-section>
    </q-card>
  </q-page>
</template>

<script>
const columns = [
  {
    name: 'id',
    label: 'ID',
    field: 'id',
    align: 'left',
    sortable: true,
    style: {
      fontSize: '14px'
    },
    headerStyle: {
      fontSize: '18px'
    }
  },
  {
    name: 'naslov',
    label: 'Naslov knjige',
    field: 'naslov',
    align: 'left',
    sortable: true,
    style: {
      fontSize: '14px'
    },
    headerStyle: {
      fontSize: '18px'
    }
  },
  {
    name: 'autor',
    label: 'Autor',
    field: 'autor',
    align: 'left',
    sortable: true,
    style: {
      fontSize: '14px'
    },
    headerStyle: {
      fontSize: '18px'
    }
  },
  {
    name: 'godina',
    label: 'Godina izdanja',
    field: 'godina',
    align: 'left',
    sortable: true,
    style: {
      fontSize: '14px'
    },
    headerStyle: {
      fontSize: '18px'
    }
  },
  {
    name: 'izdavac',
    label: 'Izdavač',
    field: 'izdavac',
    align: 'left',
    sortable: true,
    style: {
      fontSize: '14px'
    },
    headerStyle: {
      fontSize: '18px'
    }
  }
]

const rows = [
  {
    id: 1,
    naslov: 'Mali princ',
    autor: 'Antoine de Saint-Exupéry',
    godina: 1943,
    izdavac: 'Mladost'
  },
  {
    id: 2,
    naslov: 'Zločin i kazna',
    autor: 'Fjodor Dostojevski',
    godina: 1866,
    izdavac: 'Školska knjiga'
  },
  {
    id: 3,
    naslov: 'Proces',
    autor: 'Franz Kafka',
    godina: 1925,
    izdavac: 'Naklada Ljevak'
  },
  {
    id: 4,
    naslov: 'Na Drini ćuprija',
    autor: 'Ivo Andrić',
    godina: 1945,
    izdavac: 'Prosveta'
  },
  {
    id: 5,
    naslov: 'Ponos i predrasude',
    autor: 'Jane Austen',
    godina: 1813,
    izdavac: 'Znanje'
  }
]

export default {
  setup () {
    return {
      popis_knjiga: 'Na ovoj stranici možete pregledati popis svih knjiga u našoj knjižnici. U tablici su prikazani osnovni podaci o knjigama, poput naslova, autora i ostalih informacija.',
      columns,
      rows
    }
  }
}
</script>

<style lang="sass" scoped>
.my-card
  width: 100%
</style>
