<script setup lang="ts">
import { useRoute } from "vue-router";
const route = useRoute();

const { data } = await useFetch<Posts>("https://jsonplaceholder.typicode.com/posts/" + route.params.id)

type Posts = {
    body: string,
    id: number,
    title: string,
    userId: number
}
const posts = data.value;

</script>
<template>
    <div>
        <h1>posts/{{ route.params.id }}</h1>
        <ul>
            <li v-if="posts">
                {{ posts.id }} : {{ posts.body }}
            </li>
        </ul>
        <NuxtLink to="/posts">Posts一覧へ</NuxtLink>
    </div>
</template>