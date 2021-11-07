<template>
    <Layout>
        <h2 class="text-4xl font-bold">Users Page</h2>
        <p class="pt-4" v-text="time"></p>
    </Layout>
</template>
<script setup>
import Layout from "../Shared/Layout"

defineProps({
    time: String
});
</script>
