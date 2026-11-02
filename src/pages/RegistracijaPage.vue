<template>
  <q-page class="q-pa-md">
    <q-card dark bordered class="bg-grey-9 my-card">
      <q-card-section>
        <div class="text-h3 text-weight-bolder text-center">
          Registracija korisnika
        </div>
      </q-card-section>

      <q-card-section class="text-h4 text-justify">
        {{ registracija }}
      </q-card-section>



      <q-card-section>
        <div class="q-pa-md">
          <div class="q-gutter-md">

            <q-input outlined v-model="ime" label="Ime" />
            <q-input outlined v-model="prezime" label="Prezime" />
            <q-input outlined v-model="korisnicko_ime" label="Korisničko ime" />
            <q-input outlined v-model="email" label="E-mail" />
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
    const ime = ref('')
    const prezime = ref('')
    const korisnicko_ime = ref('')
    const email = ref('')
    const lozinka = ref('')

    return {
      registracija: 'Za izradu korisničkog računa potrebno je ispuniti obrazac s osobnim podacima. Nakon unosa svih potrebnih podataka odaberite gumb Potvrdi kako biste dovršili registraciju.',
      ime,
      prezime,
      korisnicko_ime,
      email,
      lozinka
    }
  }
}
</script>

<style lang="sass" scoped>
.my-card
  width: 100%
</style>