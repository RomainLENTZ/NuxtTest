<template>
    <main>
        <h1>Produit {{ id }} </h1>
        <nuxt-link to="/">home</nuxt-link>
    </main>
</template>

<script setup lang="ts">
    const route = useRoute();
    const { id } = route.params

    console.log(id);
</script>