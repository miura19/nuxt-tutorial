<script setup lang="ts">

import { ref } from 'vue'
const name = ref<String>("nanami")
const counter = ref(0)
const countUp = () => {
    counter.value++
}

const { data } = await useFetch<User[]>("https://jsonplaceholder.typicode.com/users");
// console.log(data.value);
const users = data.value

type Geo = {
    lat: string;
    lng: string;
};

type Address = {
    street: string;
    suite: string;
    city: string;
    zipcode: string;
    geo: Geo;
};

type Company = {
    name: string;
    catchPhrase: string;
    bs: string;
};

type User = {
    id: number;
    name: string;
    username: string;
    email: string;
    address: Address;
    phone: string;
    website: string;
    company: Company;
};

</script>
<template>
    <div>
        <h1>トップページ</h1>
        <hr />
        <h1>hello Nuxt!</h1>
        <h2>{{ name }}</h2>
        <button @click="countUp">ボタン</button>
        <h2>{{ counter }}</h2>
        <NuxtLink to="./price">price</NuxtLink>
        <ul>
            <li v-for="user in users" :key="user.id">{{ user.id }} {{ user.name }}</li>
        </ul>
    </div>
</template>