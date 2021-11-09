<template>
    <Head title="Create User"/>
    <h1 class="text-3xl">Create New User</h1>

    <form @submit.prevent="submit" class="max-w-md mx-auto mt-8">
        <div class="mb-6">
            <label for="name" class="block md-2 uppercase font-bold text-xs text-gray700">
                Name
            </label>
            <input v-model="form.name" type="text" class="border border-gray-400 p-2 w-full" name="name" id="name" required>
            <div v-if="$page.props.errors.name" v-text="$page.props.errors.name" class="text-red-500 text-xs mt-1 mb-4" />

            <label for="email" class="block md-2 uppercase font-bold text-xs text-gray700">
                Email
            </label>
            <input v-model="form.email" type="email" class="border border-gray-400 p-2 w-full" name="email" id="email" required>
            <div v-if="$page.props.errors.email" v-text="$page.props.errors.email" class="text-red-500 text-xs mt-1 mb-4" />

            <label for="password" class="block md-2 uppercase font-bold text-xs text-gray700">
                Password
            </label>
            <input v-model="form.password" type="password" class="border border-gray-400 p-2 w-full" name="password" id="password" required>
            <div v-if="$page.props.errors.password" v-text="$page.props.errors.password" class="text-red-500 text-xs mt-1 mb-4" />

        </div>

        <div class="md-6">
            <button class="bg-green-600 text-white rounded py-2 px-4 hover:bg-green-700">
                Submit
            </button>
        </div>
    </form>
</template>

<script setup>
import {reactive} from "vue";
import {Inertia} from "@inertiajs/inertia";

let form = reactive({
    name: '',
    email: '',
    password: '',
});

let submit = () => {
    Inertia.post('/users', form);
}
</script>

<style scoped>

</style>
