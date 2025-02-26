<script>
import { nextTick, ref } from 'vue';
export default {
    setup(){
        const myNumber = ref(0);
        const name = ref("");
        const people = ref({
          information: { jumlah: 2 },
          arr: ['Rizdhan', 'Arnold'],
        });
        

        function changeNumber() {
          return myNumber.value++
        }

        function addName() {
          people.value.information.jumlah++;
          people.value.arr.push(name.value);
          name.value = "";
        }

        function deleteName(index) {
          people.value.information.jumlah--;
          people.value.arr.splice(index, 1); 
        }

        return {
            myNumber, changeNumber, name, addName, people, deleteName
        }
    }
}
</script>
<template>
  <div class="container mt-3">
    <h1>{{ myNumber }}</h1>
    <h1>Rizdhan Hernanda Rachmansyah</h1>
    <button @click="changeNumber()">Test</button>
  </div>
  <div class="container mt-3">
    <div class="mb-3">
      <label>Name</label>
      <input type="text" v-model="name" class="form-control"/>
     
    </div>
     <button type="button" class="btn btn-primary" @click="addName">Add</button>
  </div>
  <div class="container mt-3">
    <div class="table-responsive">
      <table class="table table-bordered">
        <thead>
          <tr>
              <th scope="col">Name</th>
              <th scope="col" width="15%">Action</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(name, index) in people.arr" :key="index">
            <td>{{name}}</td>
            <td><button @click="deleteName(index)" class="btn btn-danger btn-sm">X</button></td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>