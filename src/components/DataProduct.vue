<script setup>
import { ref, reactive } from "vue";

const props = defineProps({
    // Prop untuk konfigurasi umum aplikasi
    titleApp: {
        type: [String, Number],
        default: 'List Data'
    },
    // Prop untuk daftar produk
    products: {
        type: Array,
        default: () => []
    }
});

</script>


<template>

   
    <div class="container">
        <h4>{{ props.titleApp }}</h4>
    <div class="d-flex justify-content-center align-items-center" style="height: 90vh;">
      <table class="table table-bordered">
        <thead>
          <tr>
            <th scope="col">#</th>
            <th scope="col">Nama</th>
            <th scope="col">Harga</th>
            <th scope="col">Stok</th>
            <th scope="col">Kategori</th>
            <th scope="col">Action</th>
          </tr>
        </thead>
        <tbody>
           
              <tr v-for="prod in props.products" :key="prod.idProduct">
            <th scope="row">{{ prod.idProduct }}</th>
            <td>{{ prod.namaProduct }}</td>
            <td>Rp{{ prod.hargaProduct.toLocaleString('id-ID') }}</td>
            <td>{{ prod.stokProduct }}</td>
            <td>{{ prod.kategoriProduct }}</td>
            <td>
                 <input type="text" class="btn btn-sm btn-warning mr-2" value="edit"> 
                 <input type="text" class="btn btn-sm btn-danger" value="hapus"> 
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>

</template>

<style scope>

</style>