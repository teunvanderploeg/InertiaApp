<template>
    <Head>
        <title>My app</title>
        <meta type="description" content="Information about the app" head-key="description">
    </Head>
    <section class="p-6 bg-gray-200">
        <header class="flex justify-between">
            <div class="flex row">
                <h1 class="font-bold text-lg">My App</h1>
                <p class="text-sm ml-4 my-auto">Welcome Back, {{ username }}</p>
            </div>
            <Nav/>
        </header>
    </section>
    <section class="p-6">
        <div class="max-w-3xl mx-auto bg-gray-200">
            <slot/>
        </div>
    </section>
</template>

<script>
import Nav from "./Nav";
import {Head} from "@inertiajs/inertia-vue3"

export default {
    name: "Layout.vue",
    components: {Nav, Head},

    computed: {
        username() {
            return this.$page.props.auth.user.username;
        }
    }
}
</script>
