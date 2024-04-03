<script setup lang="ts">

const { data } = await useFetch<Posts[]>('https://jsonplaceholder.typicode.com/posts/');

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
        <h1>Posts一覧</h1>
        <nuxt-link to="/">トップページへ</nuxt-link>
        <ul>
            <li v-for="post in posts" :key="post.id"><NuxtLink to="`/posts/${post.id}`">{{post.id}} : {{ post.title }}</NuxtLink></li>
        </ul>
    </div>
</template>