<template>
        <h2 class="text-4xl font-bold">Users Page</h2>
        <p class="pt-4" v-text="time"></p>
</template>
<script>
import Layout from "../Shared/Layout"

export default {
    layout: Layout,
    props: { time: String},
}
</script>
