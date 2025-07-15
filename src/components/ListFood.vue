<script setup>
import { reactive, ref } from "vue";
import DataFoods from './FoodData.vue'
const dataProduk = ref([
  {
    idFood: 1,
    namaFood: 'Rendang Daging Sapi 500gr',
    hargaFood: 75000,
    stockFood: 20,
    kategoriFood: 'Makanan'
  },
  {
    idFood: 2,
    namaFood: 'Kopi Gayo Arabica 250gr',
    hargaFood: 45000,
    stockFood: 40,
    kategoriFood: 'Minuman'
  },
  {
    idFood: 3,
    namaFood: 'Keripik Balado Padang 200gr',
    hargaFood: 25000,
    stockFood: 50,
    kategoriFood: 'Makanan'
  },
  {
    idFood: 4,
    namaFood: 'Sambal Roa Asli Manado 150gr',
    hargaFood: 30000,
    stockFood: 35,
    kategoriFood: 'Makanan'
  },
  {
    idFood: 5,
    namaFood: 'Teh Hijau Gunung Slamet 100gr',
    hargaFood: 20000,
    stockFood: 60,
    kategoriFood: 'Minuman'
  },
  {
    idFood: 6,
    namaFood: 'Bakpia Pathok Isi Kacang Hijau',
    hargaFood: 30000,
    stockFood: 25,
    kategoriFood: 'Makanan'
  },
  {
    idFood: 7,
    namaFood: 'Dodol Garut 250gr',
    hargaFood: 22000,
    stockFood: 30,
    kategoriFood: 'Makanan'
  },
  {
    idFood: 8,
    namaFood: 'Minuman Jahe Merah Instan 10 Sachet',
    hargaFood: 27000,
    stockFood: 45,
    kategoriFood: 'Minuman'
  },
  {
    idFood: 9,
    namaFood: 'Emping Melinjo Pedas Manis 200gr',
    hargaFood: 28000,
    stockFood: 32,
    kategoriFood: 'Makanan'
  },
  {
    idFood: 10,
    namaFood: 'Susu Kedelai Murni Botol 500ml',
    hargaFood: 15000,
    stockFood: 40,
    kategoriFood: 'Minuman'
  },
  {
    idFood: 11,
    namaFood: 'Kue Lumpur Kentang 5 pcs',
    hargaFood: 20000,
    stockFood: 20,
    kategoriFood: 'Makanan'
  },
  {
    idFood: 12,
    namaFood: 'Cendol Dawet Ayu 400ml',
    hargaFood: 12000,
    stockFood: 35,
    kategoriFood: 'Minuman'
  },
  {
    idFood: 13,
    namaFood: 'Brem Bali Tradisional 100gr',
    hargaFood: 18000,
    stockFood: 28,
    kategoriFood: 'Minuman'
  },
  {
    idFood: 14,
    namaFood: 'Getuk Lindri Ubi Ungu 250gr',
    hargaFood: 23000,
    stockFood: 18,
    kategoriFood: 'Makanan'
  },
  {
    idFood: 15,
    namaFood: 'Es Kopi Susu Gula Aren Botol 250ml',
    hargaFood: 18000,
    stockFood: 50,
    kategoriFood: 'Minuman'
  }
]);

function handleAddFood() {
  const newId = dataProduk.value.length + 1
  dataProduk.value.push({
    idFood: newId,
    namaFood: 'Produk Baru ' + newId,
    hargaFood: 12345,
    stockFood: 10,
    kategoriFood: 'Makanan'
  })
}

function handleDeleteFood(idFood) {
  const index = dataProduk.value.findIndex(item => item.idFood === idFood)
  if (index !== -1) {
    const nama = dataProduk.value[index].namaFood
    dataProduk.value.splice(index, 1)

    // Tambahkan jeda 1 detik (1000ms) sebelum alert muncul
    setTimeout(() => {
      alert(`Produk "${nama}" berhasil dihapus`)
    }, 1000)
    
  } else {
    alert('Produk tidak ditemukan!')
    console.warn('ID tidak ditemukan:', idFood)
  }
}



function handleUpdateFood(updatedItem) {
  const index = dataProduk.value.findIndex(item => item.idFood === updatedItem.idFood)
  if (index !== -1) {
    dataProduk.value[index] = { ...updatedItem } // replace with new data
    alert('Produk berhasil di-update!')
  }
}


</script>

<template>
    <div>
        <DataFoods :foods="dataProduk" @add-food="handleAddFood" @delete-food="handleDeleteFood" @update-food="handleUpdateFood"/>
    </div>
</template>

<style>
</style>