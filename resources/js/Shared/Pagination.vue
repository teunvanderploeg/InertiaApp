<template>
    <div>
        <Component :is="link.url ? 'Link' : 'span'"
                   class="mx-1"
                   :class="{ 'text-gray-500' : ! link.url, 'font-bold' : link.active,}"
                   v-for="link in links"
                   :href="link.url"
                   v-html="link.label"/>
    </div>
</template>

<script>
export default {
    name: "Pagination",
    props: {
        links: Array,
    }
}
</script>
