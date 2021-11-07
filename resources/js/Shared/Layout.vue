<template>
    <Head>
        <title>My app</title>
        <meta type="description" content="Information about the app" head-key="description">
    </Head>

    <Menu />
    <section class="p-6">
        <div class="max-w-3xl mx-auto">
            <slot/>
        </div>
    </section>
</template>

<script>
import Nav from "./Nav";
import {Head} from "@inertiajs/inertia-vue3"
import Menu from "./Menu";

export default {
    name: "Layout.vue",
    components: {Menu, Nav, Head},

    computed: {
        username() {
            return this.$page.props.auth.user.username;
        }
    }
}
</script>
