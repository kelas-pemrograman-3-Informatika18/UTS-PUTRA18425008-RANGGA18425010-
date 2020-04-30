<template>
  <q-page padding>
    <q-card flat>
      <q-card-section class="q-gutter-md">
        <div class="text-h5">inputData</div>
        <q-form
          @submit="onSubmit"
          @reset="onReset"
          class="q-mt-lg"
        >
        <div class="q-gutter-md">
          <q-input label="namabarang" v-model="nama_barang" filled  :rules="[ val => val && val.length > 0 || 'Tolong isi barang']"></q-input>
          <q-input label="hargabarang" v-model="harga_barang" filled :rules="[ val => val && val.length > 0 || 'tolong isi hargabarang']"></q-input>
          <q-input label="stok" v-model="stok_barang" filled :rules="[ val => val && val.length > 0 || 'tolong isi  stok']"></q-input>
          <q-input label="laporan" v-model="laporan" filled :rules="[ val => val && val.length > 0 || 'tolong isi  laporan']"></q-input>
          <q-btn label="Input" type="submit" color="teal" unelevated></q-btn>
          <q-btn label="Reset" type="reset" color="teal" flat unelevated></q-btn>
        </div>
        </q-form>
      </q-card-section>
    </q-card>
  </q-page>
</template>
<script>
export default {
  data () {
    return {
      nama_barang: null,
      harga_barang: null,
      stok: null,
      laporan: null
    }
  },
  methods: {
    onReset () {
      this.nama_barang = null
      this.harga_barang = null
      this.stok_barang = null
      this.laporan = null
    },
    onSubmit () {
      this.$q.notify({
        type: 'positive',
        message: 'Berhasil Input'
      })
      this.$router.push({ name: 'dashboard' })
    }
  }
}
</script>
