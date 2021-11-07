<template>
    <Head title="Users"/>
    <h2 class="text-4xl font-bold">Users Page</h2>
    <ul>
        <li v-for="user in users" :key="user.id" v-text="user.name" />
    </ul>
</template>
<script setup>
defineProps({users: Array})
</script>
