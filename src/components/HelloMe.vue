<script setup>
import { computed, nextTick, reactive, ref } from 'vue';
const array = reactive({ count: 0 });
const count = ref(0);
const author = reactive({
    name: "Rizdhan Hernanda",
    books: ["Harry Potter", "Final Fantasy", "Naruto"]
});

const firstName = ref("Rizdhan");
const lastName = ref("Hernanda");

async function increaseCount() {
    array.count++;
    await nextTick();   
}   

const publishedBooks = computed(() => {
    return author.books.length > 0 ? author.books.length : 0
});

const fullName = computed({
    get() {
        return firstName.value + ' ' + lastName.value;
    }, set(value) {
        const name = value.split(' ');
        if (name.length > 1) {
           firstName.value = name[0];
           lastName.value = name[1]; 
        } else if(name.length === 1) {
            firstName.value = name[0];
        } else {
            firstName.value = '';
            lastName.value = '';
        }  
    }
});

const increment = computed((prev) => {
    console.log(prev);
    return count.value + 1;
});

</script>
<template>
    <div class="container mt-3">
        <h1>{{array.count}}</h1>
        <button @click="increaseCount" class="btn btn-primary btn-sm">Counter +</button>
    </div>
    <div class="container mt-3">
        <h1>Author : {{author.name}}</h1>
        <h1>Published Books : {{ publishedBooks }}</h1>
        <ul v-if="publishedBooks > 0"> 
            <li  v-for="(bk,index) in author.books" :key="index">{{bk}}</li>
        </ul>
        <p v-else>Data Tidak Ditemukan</p>
    </div>
    <div class="container mt-3">
        <h1>{{fullName}}</h1>
        <input type="text" class="form-control" v-model="fullName"/>
    </div>
    <div class="container mt-3">
        <h1>{{increment}}</h1>
        <button @click="increment" class="btn btn-primary btn-sm">Counter +</button>
    </div>
</template>