<script setup>
import { ref, reactive } from "vue";
import ProductData from './DataProduct.vue'

const dataProduk = reactive([
  {
    idProduct: 1,
    namaProduct: 'Laptop Gaming X1',
    hargaProduct: 15000000,
    stokProduct: 10,
    kategoriProduct: 'Elektronik'
  },
  {
    idProduct: 2,
    namaProduct: 'Smartphone Z Pro',
    hargaProduct: 8500000,
    stokProduct: 25,
    kategoriProduct: 'Elektronik'
  },
  {
    idProduct: 3,
    namaProduct: 'Keyboard Mekanikal RGB',
    hargaProduct: 1200000,
    stokProduct: 50,
    kategoriProduct: 'Aksesoris Komputer'
  },
  {
    idProduct: 4,
    namaProduct: 'Mouse Gaming Ergonomis',
    hargaProduct: 500000,
    stokProduct: 30,
    kategoriProduct: 'Aksesoris Komputer'
  },
  {
    idProduct: 5,
    namaProduct: 'Monitor UltraWidProducte 27 Inci',
    hargaProduct: 4000000,
    stokProduct: 15,
    kategoriProduct: 'Elektronik'
  },
  {
    idProduct: 6,
    namaProduct: 'Headset Wireless Surround',
    hargaProduct: 950000,
    stokProduct: 20,
    kategoriProduct: 'Aksesoris Komputer'
  },
  {
    idProduct: 7,
    namaProduct: 'Webcam Full HD',
    hargaProduct: 650000,
    stokProduct: 18,
    kategoriProduct: 'Aksesoris Komputer'
  },
  {
    idProduct: 8,
    namaProduct: 'Charger Cepat 65W',
    hargaProduct: 350000,
    stokProduct: 40,
    kategoriProduct: 'Elektronik'
  },
  {
    idProduct: 9,
    namaProduct: 'Tablet Edukasi Anak',
    hargaProduct: 3200000,
    stokProduct: 12,
    kategoriProduct: 'Elektronik'
  },
  {
    idProduct: 10,
    namaProduct: 'Power Bank 20000mAh',
    hargaProduct: 450000,
    stokProduct: 35,
    kategoriProduct: 'Elektronik'
  },
  {
    idProduct: 11,
    namaProduct: 'Kipas Laptop Portable',
    hargaProduct: 150000,
    stokProduct: 45,
    kategoriProduct: 'Aksesoris Komputer'
  },
  {
    idProduct: 12,
    namaProduct: 'Lampu LED RGB Meja',
    hargaProduct: 250000,
    stokProduct: 28,
    kategoriProduct: 'Aksesoris Komputer'
  },
  {
    idProduct: 13,
    namaProduct: 'Speaker Bluetooth Stereo',
    hargaProduct: 800000,
    stokProduct: 22,
    kategoriProduct: 'Elektronik'
  },
  {
    idProduct: 14,
    namaProduct: 'SSD Eksternal 1TB',
    hargaProduct: 1700000,
    stokProduct: 16,
    kategoriProduct: 'Aksesoris Komputer'
  },
  {
    idProduct: 15,
    namaProduct: 'Smartwatch Seri 6',
    hargaProduct: 2200000,
    stokProduct: 14,
    kategoriProduct: 'Elektronik'
  }
]);

</script>


<template>
    
      <ProductData   :products="dataProduk"/>
  
</template>

<style scope>

</style>