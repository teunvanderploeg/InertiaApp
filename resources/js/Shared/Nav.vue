<template>
    <nav class="mt-6">
        <ul class="list-disc">
            <li><Link href="/home" class="text-blue-800 hover:underline">Home</Link></li>
            <li><Link href="/users" class="text-blue-800 hover:underline">Users</Link></li>
            <li><Link href="/settings" class="text-blue-800 hover:underline">Settings</Link></li>
            <li><Link href="/logout" method="post" :data="{ foo: 'bar' }" as="button" class="text-blue-800 hover:underline">Logout</Link></li>
        </ul>
    </nav>
</template>

<script>
import { Link } from '@inertiajs/inertia-vue3'

export default {
    name: "Nav",
    components: { Link },
}
</script>

<style scoped>

</style>
