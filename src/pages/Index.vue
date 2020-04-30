<template>
  <q-page padding>
    <q-table
      title="inputData"
      :data="data"
      :columns="columns"
      row-

key="name"
    >
      <template v-slot:body="props">
        <q-tr :props="props">
          <q-td key="nama barang" :props="props">
            {{ props.row.nama }}
          </q-td>
          <q-td key="harga barang" :props="props">
            {{ props.row.harga }}
          </q-td>
          <q-td key="stok barang" :props="props">
            {{ props.row.stok_barang }}
          </q-td>
          <q-td key="laporan" :props="props">
            {{ props.row.laporan }}
          </q-td>
          <q-td key="aksi" :props="props">
            <div class="row">
             <div class="col">
                <q-btn label="edit" color="primary" icon="edit" unelevated ></q-btn>
              </div>
              <div class="col">
                <q-btn label="hapus" color="positive" icon="delete" unelevated ></q-btn>
              </div>
            </div>
          </q-td>
        </q-tr>
      </template>
    </q-table>
  </q-page>
</template>

<script>
export default {
  name: 'PageIndex',
  data () {
    return {
      columns: [
        {
          name: 'nama barang',
          required: true,
          label: 'nama barang',
          align: 'left',
          field: 'nama barang',
          sortable: true
        },
        { name: 'harga barang', label: 'harga barang', field: 'harga barang', align: 'center', sortable: true },
        { name: 'stok barang', label: 'stok barang ', field: 'stok barang', align: 'center', sortable: true },
        { name: 'laporan', label: 'laporan', field: 'laporan', align: 'center', sortable: true },
        { name: 'aksi', label: 'aksi', field: 'aksi', align: 'center' }
      ],
      data: [
        {
          nama: 'pensil',
          harga: '3000',
          stok_barang: '20',
          laporan: 'itemBarangMasuk'
        },
        {
          nama: 'penghapus',
          harga: '3000',
          stok_barang: '30',
          laporan: 'itemBarangKeluar'
        }
      ]
    }
  }
}
</script>
