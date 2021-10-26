<template>
    <h1 class="text-4xl font-bold">Users Page</h1>
    <Nav/>

    <div class="" style="margin-top: 1000px">
        <p>The current time is {{ time }}.</p>
    </div>
    <Link href="/users" class="text-blue-500" preserve-scroll>refresh</Link>
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
