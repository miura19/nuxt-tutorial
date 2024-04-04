<script setup lang="ts"></script>
<template>
    <div class="container">
        <header>Nuxt App</header>
        <!-- 下記slotは、NuxtLayoutコンポーネントの子要素に差し代わる -->
        <slot />
        <footer>&copy; Miura</footer>
    </div>
</template>

<style>

body{
    background-color: #eeee;
}
.container{
    max-width: 890px;
    margin: 0 auto;
    padding: 24px;
}
header{
    background: cyan;
    padding: 12px;
    border-radius: 8px;
}

footer{
    background: coral;
    padding: 12px;
    border-radius: 8px;
    margin-top: 12px
}

ul {
    list-style: none;
}
</style>