<template>
    <Disclosure as="nav" class="bg-green-800" v-slot="{ open }">
        <div class="max-w-7xl mx-auto px-2 sm:px-6 lg:px-8">
            <div class="relative flex items-center justify-between h-16">
                <div class="absolute inset-y-0 left-0 flex items-center sm:hidden">
                    <!-- Mobile menu button-->
                    <DisclosureButton class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-white hover:bg-green-700 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white">
                        <span class="sr-only">Open main menu</span>
                        <MenuIcon v-if="!open" class="block h-6 w-6" aria-hidden="true" />
                        <XIcon v-else class="block h-6 w-6" aria-hidden="true" />
                    </DisclosureButton>
                </div>
                <div class="flex-1 flex items-center justify-center sm:items-stretch sm:justify-start">
                    <div class="hidden sm:block sm:ml-6">
                        <div class="flex space-x-4">
                            <Link v-for="item in navigation" :key="item.name" :href="item.href" :class="['px-3 py-2 rounded-md text-sm font-medium', $page.component === item.name ? 'bg-green-900 text-white' : 'text-gray-300 hover:bg-green-700 hover:text-white']">{{ item.name }}</Link>
                        </div>
                    </div>
                    <div class="flex-shrink-0 flex items-center ml-auto">
                        <span class="text-white text-xl">{{ username }}</span>
                    </div>
                </div>
            </div>
        </div>

        <DisclosurePanel class="sm:hidden">
            <div class="px-2 pt-2 pb-3 space-y-1">
                <Link v-for="item in navigation"  :key="item.name" :href="item.href" :class="['block px-3 py-2 rounded-md text-base font-medium', $page.component === item.name ? 'bg-green-900 text-white' : 'text-gray-300 hover:bg-green-700 hover:text-white']">{{ item.name }}</Link>
            </div>
        </DisclosurePanel>
    </Disclosure>
</template>

<script>
import { Disclosure, DisclosureButton, DisclosurePanel, MenuButton } from '@headlessui/vue/dist'
import { MenuIcon, XIcon } from '@heroicons/vue/outline'
import NavLink from "./NavLink";
const navigation = [
    { name: 'Home', href: '/home'},
    { name: 'Users', href: '/users'},
    { name: 'Settings', href: '/settings'},
]

export default {
    components: {
        Disclosure,
        DisclosureButton,
        DisclosurePanel,
        MenuButton,
        MenuIcon,
        XIcon,
        NavLink,
    },
    computed: {
        username() {
            return this.$page.props.auth.user.username;
        }
    },
    setup() {
        return {
            navigation,
        }
    },
}
</script>
