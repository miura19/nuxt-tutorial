<script setup lang="ts">
useHead({
	title: "Nuxt Tutorial", // titleタグ設定
});
</script>

<template>
	<div>
		<!-- <NuxtWelcome /> -->
		<NuxtLayout>
			<NuxtPage />
		</NuxtLayout>
	</div>
</template>

<style>

.page-enter-active,
.page-leave-active {
	transition: all 0.4s;
}

.page-enter-from,
.page-leave-to {
	opacity: 0;
	filter: blur(1rem);
}
</style>