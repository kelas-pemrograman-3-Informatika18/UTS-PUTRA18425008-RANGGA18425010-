<template>
  <q-page class="bg-red-3">
      <div class="row">
        <q-card class="fixed-center col-md-4 col-xs-12 bg-grend" flat>
          <q-card-section>
            <div class="text-h6 q-pb-md">
            halaman login minimarket
            </div>
          <q-form
          @reset="onReset"
          @submit="onSubmit"
          class="q-gutter-md"
          >
            <q-input
              filled
              v-model="Username"
              label="UserName"
              hint="Username"
              lazy-rules
            :rules="[ val => val && val.length > 0 || 'Masukkan Username Anda']"
            />

            <q-input
              filled
              v-model="password"
              label="Password"
              lazy-rules
              :rules="[ val => val && val.length > 0 || 'Masukkan Password Anda' ]"
              />
            <div>
              <q-btn label="Submit" type="submit" color="red"/>
              <q-btn label="Reset" type="reset" color="red" flat class="q-ml-sm" />
            </div>
          </q-form>
        </q-card-section>
      </q-card>
    </div>
  </q-page>
</template>
<script>
export default {
  data () {
    return {
      Username: null,
      password: null
    }
  },
  methods: {
    onSubmit () {
      if (this.Username === 'putra' && this.password === '12345') {
        this.$q.notify({
          type: 'positive',
          message: ' anda berhasil login ;)'
        })
        this.$router.push('/home')
      } else {
        this.$q.notify({
          type: 'negative',
          message: 'password anda salah '
        })
      }
    },
    onReset () {
      console.log('ini fungsi submit')
    }
  }
}
</script>
