<script setup lang="ts">
const route = useRoute()

const { data } = await useAsyncData(`content-${route.path}`,() =>
    queryContent().where({ _path: route.path }).findOne()
)
</script>

<template>
    <main>
        <header>
            <h4> {{ data.title }}</h4>
            <span class="text-gray-400"> by {{ data.author }}</span>
        </header>
        <ContentRenderer :value="data"/>
    </main>
</template>

<style scoped>
main {
    @apply pt-7 px-4 font-rubik;
}

main :deep(h1) {
    @apply text-gray-700 text-2xl mb-3 mt-3;
}

main :deep(h4) {
    @apply text-black font-bold text-4xl mb-2;
}

main :deep(p) {
    @apply text-justify;
}

</style>