<script setup>
import { ref, computed } from "vue";
const emit = defineEmits(['add-food','delete-food', 'update-food'])
const titleTable = ref('List Product Alfamart');

const propsFood = defineProps({
       foods:{
        type:Array,
        default: () => []
       }
})

function addData(){
    emit('add-food')
}

function deleteItem(idFood){
 const yakin = confirm('Apakah kamu yakin ingin menghapus produk ini?')
  if (yakin) {
    emit('delete-food', idFood)
  }
}


const isEditing = ref(false)
const editedItem = ref({})

function startUpdate(food) {
  isEditing.value = true
  editedItem.value = { ...food } // copy data
}

function saveUpdate() {
  emit('update-food', editedItem.value)
  isEditing.value = false
  editedItem.value = {}
}

const keyword = ref('');
// Computed untuk filter berdasarkan keyword
const filteredFoods = computed(() => {
  if (!keyword.value) return propsFood.foods

  return propsFood.foods.filter(food =>
    food.namaFood.toLowerCase().includes(keyword.value.toLowerCase()) ||
    food.kategoriFood.toLowerCase().includes(keyword.value.toLowerCase())
  )
})


</script>

<template>
     <div class="container">
        <h4>{{ titleTable }}</h4>
          <div v-if="isEditing" class="mb-3 p-3 border rounded">
            <h5>Edit Produk</h5>
            <input v-model="editedItem.namaFood" class="form-control mb-2" placeholder="Nama Produk" />
            <input v-model.number="editedItem.hargaFood" type="number" class="form-control mb-2" placeholder="Harga" />
            <input v-model.number="editedItem.stockFood" type="number" class="form-control mb-2" placeholder="Stok" />
            <input v-model="editedItem.kategoriFood" class="form-control mb-2" placeholder="Kategori" />
            <button class="btn btn-success me-2" @click="saveUpdate">Simpan</button>
            <button class="btn btn-secondary" @click="isEditing = false">Batal</button>
            </div>


     <div class="row mb-0">
     <div class="col">
    <div class="d-flex justify-content-between align-items-center">
 
      <!-- button add -->
      <button class="btn btn-primary btn-sm" @click="addData">Add Data</button>

       <!-- component Cari -->
       <input
        v-model="keyword"
        type="text"
        placeholder="Cari produk..."
        class="form-control col-md-4"
       />
    </div>
  </div>
</div>


    <div class="d-flex justify-content-center align-items-center" style="height: 80vh;">
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

        <tr v-if="filteredFoods.length === 0">
      <td colspan="6" class="text-center text-muted">
        🔍 Tidak ditemukan data yang cocok dengan pencarian.
      </td>
    </tr>


             <tr v-for="food in filteredFoods" :key="food.idFood">
                 <td>{{ food.idFood }}</td>
                 <td>{{ food.namaFood }}</td>
                 <td>{{ food.hargaFood }}</td>
                 <td>{{ food.stockFood }}</td>
                 <td>{{ food.kategoriFood }}</td>
                 <td>
                     <button class="btn btn-warning btn-sm mr-2" @click="startUpdate(food)">Update</button>
                    <button class="btn btn-danger btn-sm" @click="deleteItem(food.idFood)">Delete</button>
                 </td>

             </tr>
            
        </tbody>
      </table>
    </div>
  </div>

</template>

<style>
</style>