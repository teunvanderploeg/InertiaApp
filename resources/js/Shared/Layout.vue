<template>
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

export default {
    name: "Layout.vue",
    components: {Nav},

    computed: {
        username() {
            return this.$page.props.auth.user.username;
        }
    }
}
</script>
