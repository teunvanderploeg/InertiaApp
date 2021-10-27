<template>
    <h1 class="text-4xl font-bold">Users Page</h1>
    <Nav/>
    <p class="pt-4" v-text="time"></p>
</template>
<script>
import Nav from "../Shared/Nav";
import {Link} from "@inertiajs/inertia-vue3"

export default {
    components: {Nav, Link},
    props: {
        time: String,
    }
};
</script>

<style scoped>

</style>
