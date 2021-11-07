<template>
        <h2 class="text-4xl font-bold">Users Page</h2>
        <p class="pt-4" v-text="time"></p>
</template>
<script>
export default {
    props: { time: String},
}
</script>
