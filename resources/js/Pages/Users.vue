<template>
    <Layout>
        <h2 class="text-4xl font-bold">Users Page</h2>
        <p class="pt-4" v-text="time"></p>
    </Layout>
</template>
<script>
import Layout from "../Shared/Layout"

export default {
    components: { Layout },
    props: { time: String},
}
</script>
