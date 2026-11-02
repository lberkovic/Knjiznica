<template>
  <q-page class="q-pa-md">
    <q-card dark bordered class="bg-grey-9 my-card">
      <q-card-section>
        <div class="text-h3 text-weight-bolder text-center">
          Prijava korisnika
        </div>
      </q-card-section>

      <q-card-section class="text-h4 text-justify">
        {{ prijava }}
      </q-card-section>


      <q-card-section>
        <div class="q-pa-md">
          <div class="q-gutter-md">

            <q-input outlined v-model="korisnicko_ime" label="Korisničko ime" />

            <q-input outlined v-model="lozinka" label="Lozinka" type="password" />

            <q-btn color="primary" label="Potvrdi" />

            
          </div>
        </div>
      </q-card-section>

    </q-card>
  </q-page>
</template>

<script>
import { ref } from 'vue'

export default {
  setup () {
    const korisnicko_ime = ref('')
    const lozinka = ref('')

    return {
      prijava: 'Unesite svoje korisničko ime i lozinku kako biste pristupili svom korisničkom računu i uslugama knjižnice.',
      korisnicko_ime,
      lozinka
    }
  }
}
</script>

<style lang="sass" scoped>
.my-card
  width: 100%
</style>